# AL_1115 최신 업로드 원고 인용 재점검 — 2026-11-17

## 대상·범위
이번 업로드 AL_1115.docx(586500 bytes, 첨부 ID file_0000000001c88209998349be0b72dd30)를 기준으로 확인했다. 원고 원본은 수정하지 않았으며 신규 온라인 문헌 검증이나 EndNote 앱 내 갱신 테스트는 수행하지 않았다.

## 현재 확인 결과
- Word XML에서 instrText 24개, fldChar 63개 확인. EN.CITE, EN.CITE.DATA, EN.REFLIST 필드가 존재한다. 이전 같은 이름 업로드에서 필드가 없었던 상태와 다르다. 다만 실제 EndNote 앱에서 갱신 가능한지는 미검증.
- 기존 References 수기 목록 14개와 문서 맨 끝 EndNote 자동 목록 16개가 동시에 존재. 최종본은 자동 목록을 References 위치로 정리하고 수기 목록을 제거해야 함. 필드 코드 문자열을 직접 편집하지 말고 Word/EndNote에서 작업.
- Park 및 Zhao는 Introduction Asian/high-volume 문장에 13,14로 인용됨. 새 자동 목록에 두 DOI가 모두 정상 표시됨: Park 10.1097/SLA.0000000000005788; Zhao 10.1001/jamasurg.2021.4568.
- Riley/Collins는 새 자동 목록 및 일부 본문 EndNote 필드에 존재. 이전 미확인 사항은 이번 원고에서는 해소됨.

## 새 자동 목록 기준 번호
1 Frye; 2 Mirnezami; 3 Ito; 4 Tsalikidis; 5 Ahmad; 6 Gan; 7 Mazaki; 8 Ochs; 9 Sakamoto; 10 Taha-Mehlitz; 11 Collins/TRIPOD+AI; 12 Riley/external validation; 13 Park/COLRAR; 14 Zhao/TDT; 15 Rahbari/ISREC; 16 Cira/editorial.

## 수정 우선순위
1. Methods / Study Design and Participants: TRIPOD+AI 문장 끝 표시가 12이나, 새 자동 목록에서 Collins는 11, Riley는 12. Collins 레코드로 인용을 다시 삽입/교체하고 Update Citations and Bibliography 후 확인. Discussion Strengths의 TRIPOD+AI 11은 새 목록과 일치.
2. 수기 References 14개와 자동 목록16개 중복 정리. 원고 전체를 과거 번호로 수동 일괄 치환하지 말 것. Ito3, Ochs8, Collins11, Riley12, Rahbari15, Cira16 등 새 번호가 실제 연결되는 레코드에 따를 것.
3. 새 목록 서지 필드 오류 수정: 저널명이 빈 1 Frye,4 Tsalikidis,7 Mazaki,11 Collins,12 Riley. 각각 Colorectal Disease, Current Oncology, Anticancer Research, BMJ, BMJ. EndNote 레코드의 Journal 필드에 입력.
4. DOI 뒤에 잘못 붙은 `%J ...` 잔재: 7 Mazaki,8 Ochs,11 Collins,12 Riley,16 Cira. DOI에는 식별자만 남기고 저널명을 Journal 필드로 정리. Frye1/Rahbari15의 DOI URL 접두부도 다른 레코드와 형식 통일 권장. Tsalikidis4는 DOI가 공란이며 원문 확인 후 입력(이 점검에서는 DOI 추정하지 않음).
5. 8 Ochs 및16 Cira 페이지가 e2538267-e / e2538274-e로 출력됨. EndNote Pages 필드와 출력 스타일을 점검해 article identifier만 출력되도록 정리.
6. Introduction 교체 전 문장은 취소선으로 남아 있음: 중복 내용으로 판단하지 않음. 다만 뒤의 `[   ]`는 취소선이 아니므로 clean copy에서 교체 전 문장과 함께 삭제. 새 문장의 13,14는 유지.
7. Discussion / High-volume surgical practice 문단에는 Need reference 메모가 남아 있으며 인용이 없음. Park의 경험·수술 표준화 방법은 일부 근거가 되지만, high-volume 때문에 intraop 변수가 덜 기여한다는 결론은 입증하지 않음. 인용 가능한 술기/경험 사실과 가설을 구분하고 필요한 최소 수정은 별도 논의.
8. Discussion / leakage rate 4.3%,7.9%가 Asia high-volume의 real-world rate를 대표한다는 문장은 일반화 범위 점검 필요. 자체 수치는 자체 결과이며 Park/Zhao로 지역 전체의 대표성이나 비장루 환자군 간 직접 비교가 입증되지는 않음. descriptive framing 권장.

## 확인된 주요 본문 연결
- Introduction resource/oncologic outcomes:1,2; risk factors/stapler:3,4; diversion/morbidity:5,6; ML:7–10; 외부 검증 가이드:11,12; Asian experienced surgeons:13,14.
- Outcome definition Rahbari15, Discussion stapler Ito3, Ochs8, implementation Cira16, external evaluation Riley12, Strengths Collins11은 새 목록과 주제 연결이 맞음.
- Introduction의 9120명/34 preoperative factors/F1 87→70 문장은 현재8 Ochs에 연결되므로 과거 수기 목록8 Taha-Mehlitz와 혼동하지 말 것. 수치와 정확한 모집단 정의의 원문 재검증은 이 파일 구조 점검만으로 완료했다고 주장하지 않음.

## 다음 순서
EndNote 레코드 정리 → Word Methods TRIPOD 인용 교체 → 중복 목록 정리 → Update Citations and Bibliography → DOI/저널/번호 확인 → Discussion Need reference 문장별 근거 검토. 원본 보존 후 작업 복사본에서 진행.
