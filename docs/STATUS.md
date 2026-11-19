# 현재 상태 — 2026-11-19

## 최신 보관본
- 사용자 요청으로 [AL_1118.docx 및 AL_new.enlx](../manuscript_versions/2026-11-18/)를 원본 그대로 저장. 저장만 수행했으며 AL_1118 내용은11/19재검토완료. EndNote네이티브연결검증은보류. AL_1117기록은이전버전기준.

## 기준과 범위
- 최신 업로드 원고: AL_1118.docx. 파일 내용은 변경하지 않고 보관.
- 논문 수치는 김하연 선생님 분석만 사용. 개인 spline 및 assistant 재학습 결과 제외.
- 교수님 문안은 가능한 유지하며, 실제 오류/새 분석과 모순되는 부분만 최소 수정.
- 기존 원자료 전처리 재검토, 신규 모델 개발, 종양 높이 기준 재문의는 현재 범위 아님.
- 본문 Figure1/2 + Supplementary eFigure1/2. 별도 Supplementary Methods 문서 없음.

## 현재 완료
- 추가 분석 설계/paired 비교/기관별·통합 Results와 보충그림 설명 작업.
- KNUH Table1 요약값 확인, seed7 temporal Brier 직접 검증.
- 기존 문헌 및 인용을 따라 확보한 Xu/Zhao/COLRAR PDF 검토. supporting source 기록 작성.
- Park/Zhao 가져오기용 RIS 작성. [references README](../references/README.md) 참조.

## 바로 다음 작업 — AL_1118 재업로드 점검 완료
- [2026-11-19 반영 확인 및 남은 교정](reviews/2026-11-19_AL_1118_recheck.md)을 최신 기준으로 사용. 이번 업로드는11/18보관본과동일.
- 핵심CI/Results·Discussion/인용수정/본문12pt/수기목록삭제반영완료. Results KNUHCI .545–.698로Table2와일치하므로이전문장삭제권고는해소.
- eTable3 .0197/AMCFull괄호정상(이전run추출공백지적철회). indㄹependent오타,Table1각주고립마침표및사용자가빼기로한EMVI설명,Discussion제목/공백등소규모교정필요.
- IRB/학위/연락처/분량빈칸확인후clean/회람준비. EndNote복원/재연결은보류. 원고직접변경하지않음.

## 김하연 회신 확인 완료 — 2026-11-18
- Table2 모델별 AUROC/paired delta CI 수신 및 Excel/CSV 일치 확인.
- eTable1 Brier .323 / eTable3 AUROC .7344 정정 확인; eTable3 delta는 회신 기준 .0197로 수정.
- eTable1 Brier 불일치 메모는 구버전 메모로 삭제. temporal 개발단계 평가 설명은 유지.
- [반영 위치 및 Table3 별도 bootstrap 처리](../references/reviews/2026-11-18_colleague_CI_integration.md), [채울 Table2 CSV](../manuscript_updates/Table2_confirmed_CI_20261118.csv).
- Word 직접 적용은 미완료. IRB 승인번호, 학위/교신 연락처 등 제출 빈칸은 여전히 확인 필요.

## 도구/검증 한계
- 업로드 PDF 직접 확인과 참고문헌 목록에서만 발견한 후보를 근거표에서 구분.
- 웹 검색 API는 마지막 확인 때403; 저장된 네트워크 초안과 현재 적용 상태를 혼동하지 않기. 사용자에게 확인되지 않은 UI 버튼 위치를 추측해 안내하지 않기.
- EndNote native 앱에서 실제 라이브러리 열기/Word 갱신은 검증하지 못함.
