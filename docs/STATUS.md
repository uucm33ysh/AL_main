# 현재 상태 — 2026-11-18

## 최신 보관본
- 사용자 요청으로 [AL_1118.docx 및 AL_new.enlx](../manuscript_versions/2026-11-18/)를 원본 그대로 저장. 저장만 수행했으며 이번 AL_1118의 내용·EndNote 연결 검증은 아직 하지 않음. 아래 AL_1117 검토는 이전 버전 기준.

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

## 바로 다음 작업 — 최신 AL_1117 검토 완료
- [최신 원고 전체 점검·폰트·남은 작업](reviews/2026-11-18_AL_1117_review.md)을 우선 기준으로 사용. 이전 AL_1115 점검보다 최신.
- Results Full Model Performance에 옛 Full AUROC CI가 남아 Table2 새 bootstrap CI와 KNUH 상한이 다름. 한 문장 삭제 권장(또는 새Table2 CI로 맞추기). Table3에는 AUROC없으며 별도bootstrap설명각주 불필요.
- Table2/Results/DiscussionCI, eTable1Brier/낡은메모삭제, eTable3AUROC 정정 반영 완료. Table2 괄호/공백 및 eTable3 .019 7 띄어쓰기 교정 필요.
- 붙여넣은9구간11pt/주변12pt 혼재, Ochs앞 preop-only 예시연결 잔재, Intro빈괄호, Table1KNUH pending각주, 마침표중복 정리.
- 이후 새16번호 참고문헌/제출빈칸/그림원본/clean회람본 정리. Word 직접 변경하지 않음.

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
