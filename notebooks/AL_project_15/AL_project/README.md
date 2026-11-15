# 대장 문합부 누출(Anastomotic Leak, AL) 위험 예측 모델 — Model Development

정제된 임상 데이터로 학습한 XGBoost + Isotonic calibration 기반 AL 위험 예측 모델 프로젝트.
최종 임상 모델은 **`single_split_seed7`** 이며, Streamlit 웹앱(`AL_risk_calculator/`)으로 배포되어 있다.

> **이 공유본은 Model Development 트랙만 담고 있습니다.** External Validation(KNUH n=781) 관련 코드·데이터·산출물은
> 이번 공유에서 제외되었으며(섹션 6 참조, 진행 예정), Model Development 구조를 먼저 확인하실 수 있도록 구성했습니다.
> PI/공유용 패키지는 별도로 [`results/share/`](results/share/) 폴더에 자체 목차(README)와 함께 유지된다.

---

## 1. 프로젝트 구조 & 데이터 흐름

```
AL_project/  (Model Development 공유본)
├── README.md                     ← (이 문서)
├── requirements.txt
├── data/                         원본·정제·내부검증 데이터
│   ├── raw.xlsx                   원본 (nb1 입력)
│   ├── cleaned.xlsx              정제 데이터 (development cohort)
│   └── Internal_validation.xlsx / Internal_validation_modified.xlsx   내부검증 코호트(n=60)
├── notebooks/                    분석 파이프라인 (1→7) + AL_results
├── models/                       seed7(최종) · seed42 · repeated_kfold
├── AL_risk_calculator/           Streamlit 배포 앱 (al_model.pkl = seed7 모델 사본)
└── results/                      산출물(지표·그림·예측)
    └── share/                    PI/공유용 번들 (자체 README 유지)
```

**데이터 흐름 (Model Development)**

```
raw.xlsx ─(nb1)─▶ cleaned.xlsx ─┬─(nb2)─▶ models/single_split_seed42/
                                ├─(nb3)─▶ models/single_split_seed7/   ★최종 임상모델
                                ├─(nb4)─▶ models/repeated_kfold/
                                ├─(nb6)─▶ valid_based 시드 선정 근거
                                └─(nb7)─▶ cv_based 시드 선정 근거

Internal_validation.xlsx + 세 모델 ─(nb5)─▶ 내부검증 지표·그림
cleaned + Internal_validation_modified + seed7 ─(AL_results)─▶ results/share/* (SHAP·지표·곡선)
```

---

## 2. 최종 모델 — `single_split_seed7`

| 항목 | 내용 |
|---|---|
| 학습 방법 | 단일 분할 (Train 60% / Validation 20% / Test 20%) |
| 랜덤 시드 | 7 |
| 하이퍼파라미터 탐색 | RandomizedSearchCV, n_iter=30 |
| 변수 | 30개 (stapler `reload`, `length` 제외) |
| Calibration | Isotonic |
| Threshold | 0.0400 (F2 최대화로 dev에서 결정한 절대값) |
| 학습 노트북 | `notebooks/3_train_single_split_seed7.ipynb` |
| 배포 | `AL_risk_calculator/` (Streamlit), `al_model.pkl` = 본 모델 사본 |

**Test set 성능** — held-out test set(n=545, AL 24명) 기준 (development cohort 전체 성능 아님)

- AUROC 0.7370 · AUPRC 0.0815 · F2 0.2691
- Recall 79.2% (24명 중 19명 탐지) · Precision 7.39%
- 특징: Recall이 양호(임상 사용성 좋음)하나 AUROC는 낮음

---

## 3. Seed 선정 방법론 (요약)

5개 시드({42, 123, 7, 2024, 999})로 변동성을 검증한 뒤 seed 7을 최종 채택했다.

**5-seed test AUROC 변동성** — 평균 **0.7621 ± 0.0327** (95% CI 0.71–0.81)

| 시드 | Test AUROC | 비고 |
|---|---|---|
| 42 | 0.8100 | 최고 (운 좋은 시드) |
| 999 | 0.7781 | |
| 2024 | 0.7693 | |
| **7** | **0.7370** | **평균에 가장 가까움 → 채택** |
| 123 | 0.7160 | 최저 |

**3단계 선정 논리 (결론만)**

| 단계 | 기준 | Test 참조 | 선정 |
|---|---|---|---|
| 1 (기존) | Test AUROC + F2, 평균 근접 | 예 | seed 7 (distance 0.0265, 최소) |
| 2 (Validation) | Validation AUROC, 평균 근접 | 아니오 | seed 7 (Valid mean 0.7393, seed7=0.7290) |
| 3 (CV) | Train-internal 5-fold CV mean AUROC | 아니오 | seed 42가 최근접이나 **seed 7 유지** |

- **핵심 발견**: CV 기반 5-seed AUROC 범위 = **0.0074** (순수 시드 효과 거의 무시 가능). Valid 기반 범위(0.0611)의 약 1/8 → 차이의 약 88%는 분할 효과.
- **결론**: Stage 3의 CV 최근접 시드는 42이지만, 시드 효과가 미미하고 seed 7이 Stage 1·2에서 일관되게 선정되어 **seed 7을 최종 유지**. Test set은 Stage 1에서만 사용되었고 Stage 2–3에서는 사용하지 않았으며 최종 모델에 1회만 평가함.
- ⚠️ **"CV가 seed 7을 선택했다"고 주장하지 말 것.**

> 논문 Methods/Results용 상세 3단계 설명과 근거표는 [`results/share/seed_selection_summary_NOTES.md`](results/share/seed_selection_summary_NOTES.md) 참조.

---

## 4. 보유 모델 비교 (3개)

| 모델 | AUROC | F2 | Recall | Precision | 특징 |
|---|---|---|---|---|---|
| `single_split_seed42` | **0.8100** | 0.3333 | 54.2% | 13.1% | 단일 분할, 운 좋은 시드 (nb2) |
| `single_split_seed7` ★ | 0.7370 | 0.2691 | **79.2%** | 7.4% | 단일 분할, 정직한 대표 (nb3) — **최종** |
| `repeated_kfold` (CV 25 folds) | 0.7024 ± 0.046 | – | – | – | 가장 엄격한 평가 (nb4) |
| `repeated_kfold` (Holdout) | 0.7958 | 0.3440 | **83.3%** | 10.3% | 단일 holdout 평가 |

- **seed42**: 5개 시드 중 최고 AUROC이나 "운 좋은 시드"로 확인됨(평균 0.7621), Recall 다소 낮음(54%).
- **repeated_kfold**: 가장 엄격(5-fold×5repeat). CV 평균(0.70)이 진짜 성능에 가깝고 Holdout 0.80은 운 좋은 분할 가능성. ⚠️ Train-Valid 격차 0.29(과적합 경향).
- seed42·repeated_kfold는 최종 채택 안 됨. **3-모델 비교 재현용으로 보존** (`models/single_split_seed42/`, `models/repeated_kfold/`).

---

## 5. 내부 검증 (Internal validation cohort, n=60)

검증 데이터: 60명 (AL 22명 36.7%, Safe 38명 63.3%). 노트북 `5_validation.ipynb`.

| 모델 | AUROC | AUPRC | F2 | Recall | Precision | Threshold | TP/FN | 학습-검증 안정성 |
|---|---|---|---|---|---|---|---|---|
| single_split_seed42 | 0.6794 | 0.4953 | 0.3500 | 0.318 | 0.583 | 0.080 | 7/15 | Low (−0.153) |
| **single_split_seed7** | **0.7273** | **0.5273** | **0.7258** | **0.818** | **0.500** | **0.040** | **18/4** | **Excellent (−0.010)** |
| repeated_kfold | 0.7255 | 0.5457 | 0.5804 | 0.591 | 0.542 | 0.050 | 13/9 | Medium (−0.095) |
| 펠로우 모델 (참고) | 0.6500 | 0.4770 | – | 0.227 | – | 0.060 | 5/17 | – |

**핵심 결론**
- **작업의 가치**: 펠로우 모델 대비 AUROC +0.077, Recall +59.1%p(22.7%→81.8%), AL 탐지 5명→18명.
- **최선 모델 = single_split_seed7**: 학습-검증 격차 −0.010(매우 안정적), Recall 81.8%.
- **한계**: Calibration 붕괴(학습 AL 4.3% vs 검증 36.7% 분포 차이) → 확률값 신뢰 낮으나 **위험도 순위는 유의미**. Precision 50%로 false alarm 다수.
- **임상 사용 모델: single_split_seed7** 확정.

산출: `validation_*_metrics.csv`, `validation_predictions.csv`, `validation_comparison.csv`, `validation_{seed7,seed42,repeated_kfold}.png`.

---

## 6. 외부 검증 (External Validation) — 진행 예정(공란)

> **이번 공유본에서는 공란입니다.** External Validation(KNUH n=781) 트랙의 코드·데이터·산출물은
> Model Development 구조 확정 후 별도로 공유될 예정입니다.
> (관련 노트북 `8_external_validation.ipynb`·`9_external_error_analysis.ipynb`,
> 전처리 `preprocess_external.py`, 외부 데이터/산출물은 이 패키지에 포함되지 않음.)

---

## 7. 주요 결정사항 기록 (전처리 · 변수)

- **Stapler 변수**: `stapler used for`, `stpler type` 사용 / `reload`, `length` 제외
- **procedure type**: UI에서 APR, Hartmann 제거
- **ycT**: 옵션 B (T카테고리 보존, T0–T4, TX)
- **ycN**: 숫자 통일 (0, 1, 2)
- **결측값**: NaN 유지
- **Independent cohort `anastomosis` 매핑**: `'Anastomosis and Transection/resection'`로 매핑 (학습 데이터의 98%를 차지하는 값)
- **eGFR 인코딩(배포 앱)**: eGFR ≥60 → 1, <60 → 0 (이미 0/1이면 그대로 통과)

---

## 8. 배포 앱 — `AL_risk_calculator/`

- 프로덕션 Streamlit 앱(V2.1, seed 7). 단일 환자 예측 + 배치 처리(CSV/Excel 업로드) 지원.
- 로드 파일: `al_model.pkl`(=seed7 CalibratedClassifierCV), `feature_list.pkl`(30개 변수 순서). 작업 디렉터리 기준 상대경로 로드 → 두 pkl이 앱과 같은 위치에 있어야 함.
- 기대 성능: test AUROC 0.737 / 내부검증 0.727.

---

## 9. 공유 패키지 — `results/share/`

PI/전달을 위한 완결 번들. 자체 목차 [`results/share/README.md`](results/share/README.md) 유지.
포함: seed 선정 근거(`seed_selection_summary*.md/.csv`), 재현 코드(`3_train_single_split_seed7.ipynb`, `7_cv_based_seed_selection.ipynb`), 성능표·곡선(`test_metrics.csv`, `internal_validation_metrics.csv`, `performance_summary.xlsx`, `test_{roc,pr}_curve.csv`), 해석(`shap_*`, `permutation_importance.csv`).
