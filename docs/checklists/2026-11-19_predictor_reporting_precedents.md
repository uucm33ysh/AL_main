# 변수 보고 방식 선행연구 검토 — 진행 상태

사용자 요청: 비슷한 임상 세팅·저널의 TRIPOD+AI 준수 예측모델 연구에서 변수 정의를 어디에 보고하는지 확인한 뒤, 별도 eTable4 필요 여부 결정. 현재 eTable4 추가는 확정하지 않음.

## 현재 직접 확인한 보조 사례
Ochs et al. JAMA Network Open 2025;8(10):e2538267. doi:10.1001/jamanetworkopen.2025.38267.
- 직접 확보된 본문 PDF3쪽 Model Development에서34개 변수와 일부범주를본문에열거.
- PDF12쪽 보충자료목차는eTable1/2 baseline characteristics, eTable3modelparameters등. 목차상독립변수정의표제목은없음. 실제보충자료전체는이번에확보하지못했으므로정의표가어디에도없다고단정할수없음.
- PDF2–3쪽Methods는TRIPOD와STROBE준수를기술하며,reference14는2015TRIPOD. TRIPOD+AI2024준수사례로분류하면안됨. 임상세팅/저널의보조비교자료로만사용.

## 추가검색 상태 및 남은 검토
EuropePMC 및 PubMed에서TRIPOD+AI/JAMA Network Open검색을시도했으나실행sandbox의proxy접속실패;승인된외부sandbox재시도도CONNECT403으로차단. runtime정책은package_managers preset/customhosts없음. 우회나환경게시를수행하지않음. 사용자에게잘못된설정UI를추측해안내하지않음.
따라서신규TRIPOD+AI준수논문을확인했다고보고하지않으며,요청한선행연구비교는미완료.

향후직접확인표의열:논문/연도/저널/임상·개발외부평가세팅/TRIPOD+AI준수명시및근거/9a·9b보고위치/변수정의·단위·범주·시점의제시방식/공식체크리스트의위치기재/우리원고에적용할최소구성.
최소2~3개적합사례의본문과보충자료/체크리스트를확인후,본문목록보완·기존표확장·보충방법·별도표중선택. 논문게재자체를완전한준수의증거로간주하지않음.

## 사건수 한문장 보완과는 별개
첨부된TRIPOD+AI체크리스트item21 원문:
“Specify the number of participants and outcome events in each analysis (e.g., for model development, hyperparameter tuning, model evaluation)”
현재Results→StudyPopulation의분할n문장을다음으로교체하는것을권장:
“The training, tuning, and held-out test subsets comprised 1635 patients (70 AL events), 545 patients (24 AL events), and 545 patients (24 AL events), respectively.”
별도표가필수인것이아니며본문·표·그림중어디든명확히보고하면됨. 환자선별/제외수item20a는이것만으로해결되지않음.
Word메모권장문구:
“TRIPOD+AI item 21: 각 분석의 환자 수와 결과 사건 수를 함께 보고하도록 권고하여, 기존 분할 인원 문장에 학습·튜닝·시험군의 AL 사건 수(70/24/24)를 병기했습니다. 수치는 seed 7 학습 노트북의 기존 저장 출력에서 확인했으며 추가 분석은 수행하지 않았습니다.”
