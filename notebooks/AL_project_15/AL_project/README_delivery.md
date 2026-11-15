# 전달 안내 — AL 위험도 예측 모델 서버 실행 산출물

- 패키지명: `AL_project_server_results_20260821.zip`
- 작성일: 2026-08-21
- 작성자: khy@chilab.kr

---

## 1. 패키지 개요

- 본 패키지는 2026-08-19 ~ 2026-08-21 서버에서 재실행한 산출물임
- 수록 범위: 데이터 7파일, 모델 5종, 결과 6군, 노트북 46파일, 스크립트 3파일
- 제외 범위: 구세대 격리 폴더(`_quarantine_old_generation_20260821/`), 백업 폴더(`models/backup/`, `data/backup/`), 빈 폴더, `.vscode/`

### 실행 환경

| 항목 | 버전 |
|---|---|
| Python | 3.10.12 |
| scikit-learn | 1.6.1 |
| xgboost | 3.0.0 |
| imbalanced-learn | 0.14.1 |
| pandas | 2.2.2 |
| numpy | 1.26.4 |
| scipy | 1.11.4 |
| joblib | 1.3.2 |

- 실행 시 환경변수 `OMP_NUM_THREADS=1`, `LOKY_MAX_CPU_COUNT=4` 지정함 (32코어 환경에서 loky 워커 SIGSEGV 회피 목적이며, 학습 결과에는 영향 없음 — 동일 `best_cv_score` 재현 확인함)

### 입력 데이터 무결성 (md5)

| 파일 | md5 | 비고 |
|---|---|---|
| `data/cleaned.xlsx` | `b7a36b597a92fd7ffefbc4bba0927b7b` | AMC, n=2725, event 118 |
| `data/external_cleaned.xlsx` | `ded199f1476c9a6e0a2f7285babf315d` | KNUH, n=781, event 62 |
| `data/external_processed.pkl` | `f9bf883a80e4f5b9a6697d310d956083` | 위 파일의 전처리 산출물 |

- `external_cleaned.xlsx` 및 `external_processed.pkl`은 `notebooks/1_data_cleaning.ipynb`로 **재생성한 수정 반영본**임
  - 수술술식 `ISR` → `uLAR` 매핑 반영 (재생성본 기준 uLAR 21건, ISR 0건)
  - 문합부 누출 `Threatened` → `Positive` 통합 반영
- 모든 산출물은 위 md5의 입력으로 학습·평가되었으며, 실행 직전 md5 대조를 통과함

---

## 2. 산출물별 핵심 수치

| 산출물 | 경로 | 임계값 | 핵심 지표 | 모델 md5 |
|---|---|---|---|---|
| AMC 단일분할 seed7 | `models/single_split_seed7/` | 0.05 | 테스트 AUROC **0.764995**, AUPRC 0.090256, 민감도 0.8333, 특이도 0.6238, Brier 0.041032 | `ceb151ce62ef41dfe2a185649dd4c1ce` |
| AMC 단일분할 seed42 | `models/single_split_seed42/` | 0.08 | 테스트 AUROC **0.780070**, AUPRC 0.151550, 민감도 0.4583, Brier 0.040112 | `4ad8d97165c6ea71f77e27c634fc794a` |
| AMC 반복 5×5 K-Fold | `models/repeated_kfold/` | 0.04 | CV 평균 AUROC 0.702476 (95% CI 0.682236–0.722716), **홀드아웃 AUROC 0.804703**, 홀드아웃 AUPRC 0.133319 | `6472473e40a8833d419f3139cb3317db` |
| KNUH 단일분할 seed7 | `models/knuh_single_split_seed7/` | 0.05 | 테스트 AUROC **0.694540**, AUPRC 0.162773, 민감도 0.75, Brier 0.068210 (n=781, test 157) | `3f239f368f20118c62a5583bd6281853` |
| 역방향 외부검증 (KNUH 모델 → AMC 전체) | `results/knuh_to_amc_external/` | 0.05 | **AUROC 0.646847**, AUPRC 0.097018, 민감도 0.7542, 특이도 0.3924, **calibration slope 0.720673** (intercept −1.326947), TN 1023 / FP 1584 / FN 29 / TP 89 | — |
| 20변수 축소모델 (정상본) | `results/stepA_regen_20260820/task1_reduced_retune/` | **0.063900** | 홀드아웃 AUROC 0.742282, AUPRC 0.104430, 민감도 0.625, 특이도 0.737044 | `1d48930b9a20b68a352ee52ac09866b0` |
| RFECV 변수선택 | `results/rfecv_seed7/` | — | 최적 변수 수 13, best CV score(average_precision) 0.104577 | — |

- 반복 K-Fold 폴드별 상세: `results/repeated_kfold_folds.csv` (25폴드)
- 20변수 축소모델의 3개 코호트 전체 비교: `results/stepA_regen_20260820/task1_reduced_retune/performance_full_vs_reduced.csv`

---

## 3. ★결함 표기 — 13변수 축소모델 (사용 금지)

- **대상**: `models/rfe_seed7/`, `results/rfe_seed7_test/`
- **판정**: 결함본임. 임상적 해석·논문 수치 인용에 **사용 금지**
- **결함 내용**
  - 선택된 임계값 **0.03398073**이 해당 모델의 예측확률 하한 **0.038020**보다 낮음
  - 결과적으로 전 표본이 양성으로 예측됨
  - 홀드아웃 테스트(n=545, event 24): TP 24 / FP 521 / FN 0 / **TN 0**, 민감도 1.0, **특이도 0.0**
  - 동일 현상이 Validation·Test·Train_full **세 코호트 전부**에서 재현됨
- **원인 구조**: 개발단계(dev) 모델에서 F2 최대화로 선택한 임계값을, 재학습된 최종 모델의 확률분포 확인 없이 그대로 적용하는 코드 경로에 기인함
- **동봉 사유**: 삭제하지 않고 **결함 증거 및 재현 확인용**으로만 동봉함
- **정상 대체본**: 축소모델이 필요한 경우 **20변수판** `results/stepA_regen_20260820/task1_reduced_retune/` 사용할 것
  - 임계값 0.063900이 검증 예측확률 범위 [0.0, 0.245278] 내부에 위치하여 동일 결함 없음
  - 특이도 0.737044(홀드아웃) / 0.763158(내부 n=60) / 0.635605(외부 KNUH)로 정상 작동 확인함

---

## 4. ★노트북 하드코딩 주의 3건 (실행 전 갱신 필요)

아래 노트북은 **구세대 값이 하드코딩**되어 있어 현행 산출물과 불일치함. 그대로 실행하면 assertion 실패 또는 잘못된 수치가 산출됨.

| 노트북 | 하드코딩 내용 | 조치 |
|---|---|---|
| `notebooks/8_external_validation.ipynb` | `EXPECT_MD5 = "9fad3b38eae19a9544c498afb4c9b4cd"` 및 `assert md5 == EXPECT_MD5`, `assert abs(THRESHOLD - 0.04) < 1e-9` | 현행 모델 md5(`ceb151ce…`)·임계값(0.05)과 불일치. 실행 전 갱신 필요 |
| `notebooks/12_rfe_test_final_main_figures_and_table2.ipynb` | `FINAL_THRESHOLD = 0.04`, `EXPECTED = {Held-out test: auroc 0.737 / Temporal validation: 0.727 / External validation: 0.630}` | 구세대 값. 실행 전 갱신 필요 |
| `notebooks/AL_results_backup.ipynb` | `assert abs(iv_auroc - 0.727) < 0.005` | 구세대 값. 실행 전 갱신 필요 |

- 본 패키지에서는 **코드를 수정하지 않고 원상 보존**함 (분석 로직 무수정 원칙). 갱신 여부·갱신 값은 협의 후 결정할 사항임

---

## 5. `*_server_run` 사본 안내

- 파일명에 `_server_run`이 붙은 노트북·스크립트는 **서버 실행용 사본**임
- 원본과의 차이는 **경로 셀뿐**임 (셀 단위 diff로 전수 확인함). 시드·분할·SMOTE·calibration·임계값 규칙·CV 구조·하이퍼파라미터·전처리·평가 로직은 원본과 동일함
- 적용된 경로 폴백 패턴:

```python
from pathlib import Path
try:
    from google.colab import drive
    drive.mount('/content/drive')
    ROOT = Path('/content/drive/MyDrive/Colab Notebooks/AL_project')
except ImportError:
    ROOT = Path('..').resolve()      # notebooks/knu/ 하위는 Path('../..')
```

- **Colab에서 작업할 경우 원본 노트북을 사용할 것.** `_server_run` 사본은 서버 재현용임
- 해당 사본 목록 (8개 노트북 + 1개 스크립트)
  - `notebooks/1_data_cleaning_knuh_run.ipynb`
  - `notebooks/2_train_single_split_seed42_server_run.ipynb`
  - `notebooks/3_train_single_split_seed7_server_run.ipynb`
  - `notebooks/4_train_repeated_kfold_server_run.ipynb`
  - `notebooks/10_rfecv_selection_JAMA_supplement_figure_EMF_server_run.ipynb`
  - `notebooks/11_rfe_model_server_run.ipynb`
  - `notebooks/knu/13_knuh_train_single_split_seed7_colab_server_run.ipynb`
  - `notebooks/knu/14_knuh_to_amc_external_validation_server_run.ipynb`
  - `scripts/reduced_model_server_run.py`

---

## 6. 그림 안내

- **10번**(`10_rfecv_selection_JAMA_supplement_figure_EMF.ipynb`) 및 **15번**(`knu/15_knuh_to_amc_external_error_analysis_EMF.ipynb`)의 그림은 **미생성** 상태임
- 사유: 서버에 **Arial 폰트 부재** 및 **Inkscape(EMF 변환기) 부재**. 라이브러리·폰트 설치는 수행하지 않음
- 대안 1: `_ARIAL` 접미사 버전(`10_…_EMF_ARIAL.ipynb`, `knu/15_…_EMF_ARIAL.ipynb`)을 **Colab에서 실행**하여 생성 가능함
- 대안 2: 곡선 재작도가 필요한 경우 동봉된 CSV 사용
  - `results/rfecv_seed7/rfecv_performance_by_n_features.csv`
  - `results/rfecv_seed7/rfecv_grouped_importance_history.csv`
  - `results/rfecv_seed7/rfecv_feature_ranking.csv`
  - `results/stepA_regen_20260820/task1_reduced_retune/rfecv_curve.csv` (+ `rfecv_curve.png` 생성본 동봉)
- 생성 완료된 그림: `results/knuh_to_amc_external/figures/` 4종(ROC, PR, calibration, confusion matrix), `results/rfe_seed7_test/test_full_vs_rfe.png`, `results/stepA_regen_20260820/task1_reduced_retune/rfecv_curve.png`

---

## 7. 미포함 항목 안내

| 항목 | 상태 | 비고 |
|---|---|---|
| 100회 반복실험 (`notebooks/knu/14_…` **Part B**, 셀 10–19) | **미실행** | 분석 방침 결정 대기로 실행 보류함. 사유·대체 분석은 메일 본문 참조. 노트북 코드 자체는 동봉되어 있어 즉시 실행 가능 |
| `AL_risk_calculator/` | **미포함** | 구세대 모델이 탑재되어 있어 제외함. 현행 모델(`ceb151ce…`, 임계값 0.05) 기반 재구성 예정 |
| 구세대 산출물 95파일 | **미포함** | 서버 측 `_quarantine_old_generation_20260821/`에 격리 보관 중이며 삭제하지 않음. 필요 시 별도 요청 |
| 백업 폴더 (`models/backup/` 51파일, `data/backup/` 7파일) | **미포함** | 서버 측 보관. 필요 시 별도 요청 |
| 15번 노트북 실행 결과 | **미실행** | 위 6항 사유(Arial·Inkscape 부재)와 동일 |

---

## 8. ★PHI(개인식별정보) 주의 — 전수 10건

**아래 파일에는 환자 식별자 컬럼이 포함되어 있음. 기관 외부 재공유·클라우드 업로드·이메일 첨부 전 반드시 비식별 처리하거나 해당 컬럼을 제거할 것.**

| # | 파일 | 식별자 컬럼 |
|---|---|---|
| 1 | `data/cleaned.xlsx` | 병원등록번호 |
| 2 | `data/raw.xlsx` | 병원등록번호 |
| 3 | `data/external_cleaned.xlsx` | SerialNo_KNUH |
| 4 | `data/External_validation_knu.xlsx` | SerialNo_KNUH |
| 5 | `data/Internal_validation.xlsx` | ID |
| 6 | `data/Internal_validation_modified.xlsx` | ID |
| 7 | `data/external_processed.pkl` | 내부 `raw`(781×36)·`cleaned`(781×32) DataFrame에 SerialNo_KNUH |
| 8 | `results/knuh_to_amc_external/knuh_model_amc_all_predictions.csv` | 병원등록번호 |
| 9 | `results/knuh_single_split_seed7/knuh_seed7_split_assignments.csv` | SerialNo_KNUH |
| 10 | `results/knuh_single_split_seed7/knuh_seed7_test_predictions.csv` | SerialNo_KNUH |

- 위 10건은 전체 포함 파일의 컬럼명 전수 점검으로 확인함
- 재현성 유지를 위해 원본 그대로 동봉하였으며, 컬럼 삭제·마스킹은 적용하지 않음
- 그 외 예측 CSV(`results/rfe_seed7_test/test_predictions_full_vs_rfe.csv` 등)는 `original_index` 기반으로 식별자를 포함하지 않음

---

## 9. 문의

- 산출물 재현·수치 검증 관련: khy@chilab.kr
