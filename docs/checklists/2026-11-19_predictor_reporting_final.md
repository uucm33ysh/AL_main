# 예측변수 보고 검토 최종 기록

## 네트워크 확인

이번 검토 환경에서 제한 없는 네트워크 정책이 적용된 상태를 확인했다. Europe PMC 홈페이지와 소문자 `/europepmc/` 검색 API가 HTTP 200을 반환했고, 문헌 검색과 유방 재건 연구의 보충자료 다운로드에 성공했다. JAMA Network Open은 셸에서 HTTP 403을 반환해 웹 열람과 Europe PMC로 본문 및 보충자료를 확인했다. 이전 환경의 CONNECT 403은 예비 검토 기록에 보관한다.

## 본문과 보충자료 비교

| 연구 | 본문의 변수 보고 | 보충자료의 변수 보고 |
| --- | --- | --- |
| Shaheen 등, 유방 재건 후 합병증 예측, JAMA Network Open, 2026 | Methods에서 변수군, EHR 추출 방법과 수술 전 기초정보의 출처를 설명했다. Table 1에는 나이 단위 및 치료·흡연 범주가 제시된다. 두 기관 자료를 합쳐 내부 평가했다. | eTable 2에 전체 모델 입력 목록, eTable 4에 변수 사전을 수록했다. 사전에는 재건 시점의 나이·BMI와 현재 흡연의 3개월 기준 등이 있다. [본문 및 보충자료](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2847773) |
| Glass 등, 신생아 저산소성 허혈성 뇌병증 예후 예측, JAMA Network Open, 2024 | Methods에서 후보 선정과 출생 후 첫 24시간 및 재가온·MRI 이후라는 두 모델의 정보 이용 시점을 설명했다. 별도 코호트에서 외부 평가했다. | eTable 1에 후보 변수와 적용 모델을 함께 제시했다. 5분 Apgar, 제대혈 또는 첫 24시간의 최저 pH, 첫 24시간 EEG처럼 일부 정의와 측정 시점을 변수명에 포함했다. [본문 및 보충자료](https://jamanetwork.com/journals/jamanetworkopen/fullarticle/2827551) |

두 논문은 TRIPOD+AI 적용을 본문에 명시했다. 이 검토는 실제 변수 보고 위치를 비교했으며 체크리스트 전체 준수 여부는 평가 범위에서 제외했다. Ochs와 Sakamoto는 임상적으로 유사한 예비 비교 사례로 남긴다.

## 우리 원고의 변수 보고

TRIPOD+AI 9a에 대응해 Methods에서 초기 후보 변수의 선택 근거를 설명한다. 9b에 대응해 Full 30개와 Preop 23개를 대조할 수 있도록 30행 보충표에 임상 변수명, 정의·범주 또는 단위, 측정 및 이용 가능 시점, 모델별 포함 여부를 담는 안을 권고한다. eTable 4 추가와 번호 부여는 보류한다. 변수 목록은 [기존 대응 목록](../../manuscript_updates/Preop23_Full30_email_confirmed_inventory_20261119.csv)을 사용한다. [TRIPOD+AI 체크리스트](https://equator-network.org/reporting-guidelines/tripod-statement/tripod-ai-checklist.html)

## 확정한 eGFR 원고 문구

> Preoperative estimated glomerular filtration rate (eGFR) was included as a binary predictor (<60 vs ≥60 mL/min/1.73 m²) in both the preoperative-only and full models.

정확히 60은 ≥60군에 속한다. 기존 노트북 검토 기록상 KNUH 외부 데이터는 ≥60을 1로 인코딩했다. AMC 개발 데이터는 기존 0/1을 보존했으며 원자료의 최초 인코딩 규칙은 확인되지 않았다. KDIGO 2024의 G2는 60–89, G3a는 45–59로 같은 경계를 사용한다. 변수명은 수술 전 eGFR 범주로 표기한다. [노트북 검토 기록](2026-11-19_notebook_predictor_flow_review.md) · [KDIGO 2024](https://kdigo.org/wp-content/uploads/2024/03/KDIGO-2024-CKD-Guideline.pdf)

Table 1에서 ≥60군의 빈도가 확인된 행에는 `Preoperative eGFR ≥60 mL/min/1.73 m², No. (%)`를 사용한다. 기존 ≤60 표기의 행은 집계가 어느 범주를 세었는지 확인 후 레이블을 맞춘다.

## 작업 재개 지점

최신 AL_1119 파일에 확정 문구를 반영하고, 기존 표의 eGFR 행은 집계 방향 확인 후 수정한다. 이번 문답에서 확정한 것은 표기와 Methods 문구이며 원고 파일 반영은 대기 중이다. 새 모델 학습과 전처리 변경은 수행하지 않았다.
