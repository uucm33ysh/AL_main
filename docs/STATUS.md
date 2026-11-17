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
1. 최신 업로드 AL_1115.docx 인용 재점검 완료: EndNote 필드 및 Park/Zhao DOI, Riley/Collins 반영 확인. 이전 같은 이름 파일의 미연결 상태와 구분.
2. [최신 인용 점검 기록](../references/reviews/2026-11-17_manuscript_citation_recheck.md)에 따라 수기14개/자동16개 목록 중복, Methods TRIPOD+AI 번호12→Collins 레코드, 저널 누락·DOI의 %J 잔재 등을 EndNote/Word에서 정리.
3. Discussion Need reference 문장별 근거와 일반화 범위를 최소 수정 원칙으로 논의. 자체 자료와 외부 근거/가설 구분.
4. 최종 원고 대조, 참고문헌/표·그림/제출 정보·clean copy 정리.

## 외부 확인 대기
- Table2: AMC/KNUH Preop AUROC CI2개와 Full−Preop 차이 paired CI2개. Discussion의 대응 [##]와 일치시켜야 함.
- eTable1 각주의 별도 final temporal Brier 비교 대상. 현재 제공 파일만으로 불일치 입증 안 됨.
- eTable3 seed7 temporal AUROC .7344 vs 메일 .7345의 실행 일치 여부 및 delta .0198의 원정밀도 확인. 반올림값끼리 빼서 임의 변경 금지.
- IRB 승인번호, 저자 학위/교신 연락처 등 원고 빈칸.

## 도구/검증 한계
- 업로드 PDF 직접 확인과 참고문헌 목록에서만 발견한 후보를 근거표에서 구분.
- 웹 검색 API는 마지막 확인 때403; 저장된 네트워크 초안과 현재 적용 상태를 혼동하지 않기. 사용자에게 확인되지 않은 UI 버튼 위치를 추측해 안내하지 않기.
- EndNote native 앱에서 실제 라이브러리 열기/Word 갱신은 검증하지 못함.
