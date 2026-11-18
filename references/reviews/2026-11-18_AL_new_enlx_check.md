# AL_new.enlx 내부 점검 — 2026-11-18

대상: 업로드file_00000000e8fc8209afcc78f736653701,31959bytes. 압축CRC검사통과, rdb/tdb 데이터베이스파일구성확인. EndNote앱에서직접열기/갱신테스트는아님. 원본미변경. 내부MYD문자열및Word명시적EndNote필드를대조한결과로필드부재를완전한네이티브검증으로단정하지않음.

## 확인됨
- 기존16문헌에대응하는제목확인.
- Park/Zhao 제목,저자,저널,DOI문자열존재. 각각10.1097/SLA.0000000000005788/10.1001/jamasurg.2021.4568.
- Frye저자문자열은Dent,O.F.로정상형태. 기존Word의Dent OJCD와달라갱신후반영확인필요. DOI는URL형태로존재.
- Tsalikidis DOI doi:10.3390/curroncol30030236 존재. DOI칸은접두어없는식별자로통일권장.

## 남은보완
- Ochs,Mazaki,Riley,Collins,Cira: DOI문자열에%J저널명이여전히붙어있음. 인용스타일이아닌레코드입력오류이며EndNote DOI칸에서%J이후제거.
- Ochs Pages e2538267-e2538267, Cira e2538274-e2538274 문자열남음. articleidentifier한개로정리.
- Frye/Tsalikidis/Mazaki/Riley/Collins의독립저널명문자열을해당레코드영역에서확인하지못함. EndNote Journal칸에서각각Colorectal Disease/Current Oncology/Anticancer Research/BMJ/BMJ확인입력.
- Ochs저자에Kollmann,, Lars처럼이중쉼표발견. 원문저자Kollmann을확인한뒤Kollmann, Lars로정리. 전체저자목록을이번에새로전수검증했다는의미는아님.

## Word재연결
- AL_new 내부DbID는AL_1117의명시적Mirnezami/Collins/Rahbari/Ito/Cira/Riley인용에서확인된ID와같음. 원래라이브러리계통을유지한정황.
- 반면AL_1117의Frye/Park명시적필드는다른DbID. Word에는다른라이브러리에서삽입한인용도혼재. 이사실만으로EndNote매칭실패를확정할수없으나전체가자동갱신된다고보장할수없음. 나머지바이너리필드의DbID까지완전검사한것은아님.
- Word복사본저장→EndNote에서enlx열어복원된AL_new라이브러리만열기→레코드수정저장→WordUpdate Citations and Bibliography→Frye/Park DOI/저자및번호출력확인. 매칭창이나미반영이있으면해당인용만새라이브러리레코드로선택/재삽입. Word인용필드수동편집/전체plain text변환불필요.
- 최신라이브러리나연결된Word가갱신되어야출력검증가능. enlx자체는Word첨부/경로연결파일이아님. 원본압축파일은GitHub에올리지않고이점검요약만기록.
