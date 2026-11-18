# 현재 상태 — 2026-11-17

## 기준과 범위
- 최신 업로드 원고: AL_1115.docx. 원고와 AL.enl 원본은 이 작업에서 변경하지 않음.
- 논문 수치는 김하연 선생님 분석만 사용. 개인 spline 및 assistant 재학습 결과 제외.
- 교수님 문안은 가능한 유지하며, 실제 오류/새 분석과 모순되는 부분만 최소 수정.
- 기존 원자료 전처리 재검토, 신규 모델 개발, 종양 높이 기준 재문의는 현재 범위 아님.
- 본문 Figure1/2 + Supplementary eFigure1/2. 별도 Supplementary Methods 문서 없음.

## 현재 완료
- 추가 분석 설계/paired 비교/기관별·통합 Results와 보충그림 설명 작업.
- KNUH Table1 요약값 확인, seed7 temporal Brier 직접 검증.
- 기존 문헌 및 인용을 따라 확보한 Xu/Zhao/COLRAR PDF 검토. supporting source 기록 작성.
- Park/Zhao 가져오기용 RIS 작성. [references README](../references/README.md) 참조.

## 바로 다음 작업
- Ochs 원문 검토 완료: 총9120명·34개·F1 .87/.70 일치. 엄격한 preoperative-only 예시로 연결하는 Intro/Discussion 두 문장은 최소 수정 권장. [대조 결과 및 11/18 순서](../references/reviews/2026-11-17_Ochs_citation_check.md) 참조. 사용자의 이번 우선 범위는 새 번호체계와 내용 적절성 확인이며 EndNote 서식 정리와 구분.

1. 최신 업로드 AL_1115.docx 인용 재점검 완료: EndNote 필드 및 Park/Zhao DOI, Riley/Collins 반영 확인. 이전 같은 이름 파일의 미연결 상태와 구분.
2. [최신 인용 점검 기록](../references/reviews/2026-11-17_manuscript_citation_recheck.md)에 따라 수기14개/자동16개 목록 중복, Methods TRIPOD+AI 번호12→Collins 레코드, 저널 누락·DOI의 %J 잔재 등을 EndNote/Word에서 정리.
3. Discussion Need reference 문장별 근거와 일반화 범위를 최소 수정 원칙으로 논의. 자체 자료와 외부 근거/가설 구분.
4. 최종 원고 대조, 참고문헌/표·그림/제출 정보·clean copy 정리.

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
