# 현재 상태 — 2026-11-19

## 현재 과제
JAMA Network Open 선행연구 2편의 본문·보충자료 직접 비교 완료. Full 30개와 Preop 23개를 대조하는 보충 변수 정의표를 권고하며 eTable 4 추가는 미확정. 수술 전 eGFR은 <60 vs ≥60 mL/min/1.73 m²로 표기하기로 확정했고 최신 원고 반영은 대기 중. [최종 검토 기록 및 원고 문구](checklists/2026-11-19_predictor_reporting_final.md). 새 모델 학습/전처리 변경/spline 결합은 하지 않음.

## 기준 원고·보관
- 최신 검토 업로드: AL_1119.docx 및 AL_1119_삭제선반영본.docx. 이 파일들은 작업 첨부 경로에 있으며 원고 자체는 수정하지 않음.
- GitHub에 원본 보관된 버전은 [AL_1118 및 AL_new.enlx](../manuscript_versions/2026-11-18/). 최신 업로드와 저장소 보관본을 혼동하지 않음.
- 김하연 기존 분석만 사용. 교수님 문안 최소 수정. 종양 높이 기준 재문의/새 원자료 처리 검토는 범위 밖.
- 본문 Figure1/2, eTable1–3/eFigure1–2 유지. 선정 흐름도 복원·Supplementary 배치는 교수님 확인 전 번호 변경 안함.

## 확인 완료
- Table2 CI 및 Results·Discussion pairedCI, eTable1 Brier .323, eTable3Full .7344/delta .0197 확인.
- Table3에는 AUROC행없음. 이전 관련 설명오류는 정정됐으며 Table3변경/별도bootstrap각주 불필요.
- Full30 목록은seed7노트북,Preop23는교수님22개+GFR추가라는김하연메일로확인. [대응목록](../manuscript_updates/Preop23_Full30_email_confirmed_inventory_20261119.csv).
- AMC학습1635/70AL,튜닝545/24,시험545/24;KNUH781/62AL. [저장출력집계](../manuscript_updates/analysis_set_counts_seed7_notebook_20261119.csv).
- 체크리스트위치는페이지번호대신정확한절·소절/표·그림명으로관리: [작업용Word](checklists/TRIPOD_AI_location_map_working_20261119.docx).

## 네트워크·선행연구 검토 상태
- 이번 검토 환경에서 제한 없는 네트워크 정책이 적용됐다. Europe PMC 홈페이지·검색 API HTTP 200 및 보충자료 다운로드 확인. 이전 접속 차단은 [예비 검토 기록](checklists/2026-11-19_predictor_reporting_preliminary_comparison.md)에 보관.
- Shaheen 및 Glass 연구의 본문과 보충자료에서 목록·정의·단위·시점을 대조했다. Ochs와 Sakamoto는 임상 유사 보조 사례다.

## 선행검토 적용 권고안
- 지정74419a6기록을적용한 [원고·보충표·메일권고안](checklists/2026-11-19_predictor_reporting_manuscript_recommendation.md). Shaheen정의사전+Glass모델별포함표를통합한30행보충표권고. eTable4번호/원고적용은미확정. 이번실행에서새원문독립검증안함.

## 보류·다음 작업
- 최신 AL_1119에 확정 eGFR 문구 반영. Table 1은 기존 집계의 범주 방향을 확인하고 레이블 적용. 보충 변수 정의표 채택과 번호는 보류.
- 원고진행시StudyPopulation에분할별및KNUH n/events병기(TRIPOD21),KNUHUnknown비율추가,정리본남은색/취소선제거. 미적용을완료로기록하지않음.
- 선정screened/excludedn와흐름도형식교수님확인. IRB/학위/교신/등록·protocol/PPI/data-code-model범위등확인필요.
- EndNote복원/연결은사용자요청으로보류. 11/24후속공유메일은계획이며발송/완료로간주하지않음.
