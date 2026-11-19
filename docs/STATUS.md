# 현재 상태 — 2026-11-19

## 현재 과제
JAMA Network Open 선행연구 2편의 본문·보충자료 직접 비교 완료. Full 30개와 Preop 23개를 대조하는 보충 변수 정의표를 권고하며 eTable 4 추가는 미확정. 수술 전 eGFR은 <60 vs ≥60 mL/min/1.73 m²로 표기하기로 확정했고 최신 원고 반영은 대기 중. [최종 검토 기록 및 원고 문구](checklists/2026-11-19_predictor_reporting_final.md). 새 모델 학습/전처리 변경/spline 결합은 하지 않음.

## 기준 원고·보관
- 최신 검토 업로드: AL_1119.docx 및 AL_1119_삭제선반영본.docx. 이 파일들은 작업 첨부 경로에 있으며 원고 자체는 수정하지 않음.
- 최신 업로드3개파일은 [2026-11-19 보관본](../manuscript_versions/2026-11-19/)에역할명으로저장(원본내용동일). 이전AL_1118/EndNote는11/18폴더보존.
- 김하연 기존 분석만 사용. 교수님 문안 최소 수정. 종양 높이 기준 재문의/새 원자료 처리 검토는 범위 밖.
- 본문 Figure1/2, eTable1–3/eFigure1–2 유지. 선정 흐름도 복원·Supplementary 배치는 교수님 확인 전 번호 변경 안함.

## 확인 완료
- Table2 CI 및 Results·Discussion pairedCI, eTable1 Brier .323, eTable3Full .7344/delta .0197 확인.
- Table3에는 AUROC행없음. 이전 관련 설명오류는 정정됐으며 Table3변경/별도bootstrap각주 불필요.
- Full30 목록은seed7노트북,Preop23는교수님22개+GFR추가라는김하연메일로확인. [대응목록](../manuscript_updates/Preop23_Full30_email_confirmed_inventory_20261119.csv).
- AMC학습1635/70AL,튜닝545/24,시험545/24;KNUH781/62AL. [저장출력집계](../manuscript_updates/analysis_set_counts_seed7_notebook_20261119.csv).
- 체크리스트위치는페이지번호대신정확한절·소절/표·그림명으로관리: [공식양식·절제목Word](../manuscript_versions/2026-11-19/03_AL_TRIPOD_AI_체크리스트초안_20261119.docx).

## 네트워크·선행연구 검토 상태
- 지정 커밋 74419a6의 다른 환경 검토에서 Europe PMC HTTP 200과 보충자료 다운로드를 확인한 결과를 사용합니다. 현재 이 대화의 네트워크와 혼동하지 않습니다. 이전 검색 차단 초안은 중복 정리했으며 Git 이력에 보존합니다.
- Shaheen 및 Glass 연구의 본문과 보충자료에서 목록·정의·단위·시점을 대조했다. Ochs와 Sakamoto는 임상 유사 보조 사례다.

## 선행검토 적용 권고안
- 지정74419a6기록을적용한 [원고·보충표·메일권고안](checklists/2026-11-19_predictor_reporting_manuscript_recommendation.md). Shaheen정의사전+Glass모델별포함표를통합한30행보충표권고. eTable4번호/원고적용은미확정. 이번실행에서새원문독립검증안함.

## 새 Word 산출물
- [현재 원고 내 eTable 4](../manuscript_versions/2026-11-19/01_AL_원고정리본_20261119.docx). eTable4가칭;30행/Preop23확인. WBC/PLT단위는확인필요각주표시. 본문직접삽입안함.
- 체크리스트는공식5열/문구/색상을유지하고위치만절제목으로간결화. 상태/후속메모는별도기록.

## 보류·다음 작업
- 최신 AL_1119에 확정 eGFR 문구 반영. Table 1은 기존 집계의 범주 방향을 확인하고 레이블 적용. 보충 변수 정의표 채택과 번호는 보류.
- 원고진행시StudyPopulation에분할별및KNUH n/events병기(TRIPOD21),KNUHUnknown비율추가,정리본남은색/취소선제거. 미적용을완료로기록하지않음.
- 선정screened/excludedn와흐름도형식교수님확인. IRB/학위/교신/등록·protocol/PPI/data-code-model범위등확인필요.
- EndNote복원/연결은사용자요청으로보류. 11/24후속공유메일은계획이며발송/완료로간주하지않음.

## 파일 정리
- 공식 양식 체크리스트·변수 보충표 Word는 이미1043bfc에서게시완료. 대체된초안8개는사용자요청으로현재트리에서삭제; [삭제/복구내역](CLEANUP_20261119.md). 최신파일은README에서바로접근.

## 최신 회람 전 확인
- [파일·메일·인용/서지대조](reviews/2026-11-19_mail_and_reference_final_check.md). eTable4단위/Methods인용/9b연결반영완료. 정리본빨간숫자·쉼표/Table1제목and만정리필요. reference기술적정리는11/24후속계획. 메일은파일저장안함.

## 사용자 승인 후 현재 공유 버전만 유지
- 최신 업로드3개파일의GitHub게시를사용자가명시승인. manuscript_versions/2026-11-19의원고2/체크리스트1을정본으로유지.
- 이전AL_1118및별도중복체크리스트·옛eTable4초안은현재트리에서삭제. 최신EndNote원본은references/libraries/AL_new.enlx로이동. 근거/로그/기존분석보존.
- 최신WBC/PLT단위는사용자확인후본문보충표에반영완료. 정리본빨강은ResultsFullModelPerformance의0.545끝5와0.698끝8,Discussionclinicalimplications의counseling뒤쉼표. 원고내용을임의수정하지않음.

## 체크리스트 미확인 사항을 좁힌 결과
- OutcomeDefinition의AL정의·임상확인절차는보고됨. 8b/8c/9c는평가자/주관적판독/블라인딩사실확인필요.
- 사용자 최종 확인: 이번 연구에서는 성별 하위집단 성능 분석을 시행하지 않았고, fairness-specific model adjustment도 시행하지 않음. AMC/KNUH 비교는 병원 간 external validation이며 성별·사회인구학적 하위집단 분석이 아님. 노트북 파일의 별도 코드/출력을 원고 대상 분석으로 잘못 연결한 이전 해석과 관련 질문을 철회. 성별 결과 추가/모델 대응 확인을 요청하지 않음.

## 최신 체크리스트 확인 상태
- 사용자확인:protocol존재/접근방식미확인,registration미확인,PPI미확인.14/18c/18d/19만공식양식보고칸갱신. 원고본문에는미확인사실추가안함.

## 최종 공유 체크리스트 표시
- 미확인항목은“확인 필요”로명시(3c/8b/8c/9a선택근거/9c/10/17승인번호/18c접근범위/18d/18e/f공유범위/19/20a/22). 확인된protocol존재/fairness조정미시행/9b표연결은유지. 최신공유파일같은경로갱신.

## Article Information 재확인
- 사용자가기재내용을확인:funding/funderrole/COI및data/code/trainedmodel은교신저자reasonable request제공원칙으로보고됨.18e/f/22의같은공유원칙재질문표시제거. protocol접근/registration/PPI/IRB/sample-size/평가자·blinding등은확인필요유지.
