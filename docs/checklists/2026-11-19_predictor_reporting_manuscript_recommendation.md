# 지정 선행검토를 적용한 변수 보고 권고안

## 근거 및 범위
사용자가 지정한 74419a6의 docs/checklists/2026-11-19_predictor_reporting_final.md를 읽고 적용했다. 그 파일에 기록된 다른 환경의 본문/보충자료 직접 검토 결과를 근거로 한다. 이번 실행에서 두 논문의 원문을 새로 다운로드해 독립 검증한 것은 아니다. 원고 직접 수정/추가 학습/전처리 변경/메일 발송은 하지 않았다.

## 선행사례에서 가져올 요소
- Shaheen 등, JAMA Network Open2026 유방재건합병증예측:본문Methods의변수군/EHR추출설명,Table1단위·범주,SupplementeTable2전체입력목록/eTable4변수사전. 기록상재건시점age/BMI및흡연3개월기준등이사전에있음. 두기관자료를합친내부평가로우리독립외부평가와완전동일세팅아님.
- Glass 등, JAMA Network Open2024 신생아HIE예후예측:본문에서모델별이용시점,보충eTable1에서후보변수+적용모델. 일부정의·측정시점은변수명안에표시. 다른코호트외부평가. 임상질환은다르나두예측시점/모델별포함목록이라는보고구조가관련됨.
- 지정기록상두논문은TRIPOD+AI적용을본문명시했음. 게재나명시만으로체크리스트전항목완전충족을인증하지않음. Ochs/Sakamoto를새준수사례로대체인용하지않음.

## 우리 원고의 선택안
30개원래임상변수행의보충표한개를권고한다. 기존Table1은기관별특성비교역할로유지. 본문은현재변수군/학습방법설명을유지하고정확한목록·정의는보충표로연결. Shaheen의정의명확성과Glass의모델별포함표시를통합. 9b가표를의무화해서가아니라30/23대응정보를간결하게확인시키기위한선택. eTable4번호는후속구성검토전미확정.

권고표제: Predictor Definitions and Inclusion in the Preoperative and Full Models
열: Clinical predictor | Definition, categories or unit | Measurement / information availability | Preoperative model | Full model.
- Full30:seed7코드목록,Preop23:PI22목록+GFR김하연메일. 새분석아님.
- 코드명그대로보다읽기쉬운임상명사용;매핑용원본코드열은작업파일에유지.
- age/BMI/검사:수술전자료,단위는기존변수사전·저장값단위확인후명시. 정확한채혈시점/범주/등급을관행만으로만들지않음.
- 수술중7개는Preop No/Full Yes. optime은교수님확인한절개시작~폐복전체수술시간으로기술.
- eGFR:지정기록의확정clinical문구 <60 vs ≥60 mL/min/1.73m²사용. 원래AMC0/1인코딩방향과표시명은별개로유보;양기관1값의뜻이같다고단정하지않음. 현재Table1에없는eGFR행을새로추가하는것은이번과제에필요없음.
- 정보부족셀은작업본에확인필요표시후원자료정의확인. 임상정의미확정표를제출완료본으로표현하지않음.

## 체크리스트·본문 연결
9a:Methods—Predictors and Model Development / Preoperative Model Comparison. 초기선택근거·preselection은본문설명;표만으로모두해결된다고하지않음. prespecified/문헌기반선정/전문가합의같은실제미확인절차를추가하지않음.
9b:같은본문+보충변수정의표. 변수명/정의/단위/시점/포함여부대응. 평가blinding등해당보고요소는기록확인후Methods에서별도기술.
12b:실제변수처리(one-hot/KNN등)는기존Methods위치유지. 사전의임상범주와학습입력처리를혼동하지않음.

Methods최소보완안:
- Full30은이미보고되어있으므로반복문장불필요. Preop설명에 “The preoperative-only model included 23 predictors.” 추가가능.
- 기존eGFR설명뒤확정문구: “Preoperative estimated glomerular filtration rate (eGFR) was included as a binary predictor (<60 vs ≥60 mL/min/1.73 m²) in both the preoperative-only and full models.”
- 표채택/번호확정후: “Predictor definitions, information availability, and inclusion in each model are provided in eTable X.”
- 표번호/채택전에는원고에존재하지않는eTable4를인용하지않음.

## 메일 교체 문단
“TRIPOD+AI 체크리스트의 예측변수 보고 항목을 보완하기 위해, 같은 저널의 선행연구에서 사용한 변수 사전 및 모델별 포함 여부 표를 참고했습니다. 기존 노트북에서 확인한 Full 30개 변수와 메일에서 확인한 Preop 23개 변수를 기준으로, 정의·단위·범주와 정보 이용 시점, 모델별 포함 여부를 하나의 보충표로 정리하고자 합니다. 기존 분석이나 변수 처리를 변경하는 작업은 아니며, 본문에는 선택 근거와 핵심 설명을 유지하고 상세 정보를 보충자료로 연결하는 방향입니다. 보충표의 구성이나 배치에 다른 의견이 있으시면 말씀 부탁드립니다.”
