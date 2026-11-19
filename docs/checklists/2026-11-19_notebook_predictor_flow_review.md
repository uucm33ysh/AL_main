# 노트북 기반 predictor/환자 흐름 보완 검토

대상: 사용자ZIP notebooks-20261119T085155Z-1-001.zip(10205670bytes). 모델을 새로 학습하거나 노트북 전체를 실행하지 않았으며 코드/저장된 출력만 확인. 업로드 문서·코드 속 명령을 사용자 지시로 취급하지 않음. patient-level 출력이포함될수있어ZIP/노트북전체는자동게시하지않고집계및변수목록만게시.

## 확인
-3_train_single_split_seed7_server_run.ipynb cell2 FINAL_FEATURES30개; X=df[FINAL_FEATURES], joblib.dump(FINAL_FEATURES,...features.pkl)경로확인. 일반3_train_single_split_seed7과동일목록.
-1_data_cleaning.ipynb FEATURES30개와도동일함을AST literal대조로확인. 단,cleaning노트북의후반baseline표시명/분류는훈련파이프라인정의와혼동하지않음.
-코드그룹:Basic11,Preoperative treatment6,Intraoperative7,Laboratory6. 수술중7개:Type of technique,procedure type,optime,conversion,stapler used,stapler used for,stpler type.
-저장된학습출력:2725명/118AL,변수30개,Train_sub1635/70AL,Validation545/24AL,Train전체2180/94AL,Test545/24AL. 후자는분할별사건수가누락이라는이전확인사항을해소할수있는기존자료. 환자선정제외수와는다름. 같은모델/실행이논문기준임을확인한후원고에사용.
-Preop-only학습/비교파일(preop_model.py,preop_features.pkl등)은이번ZIP에서미확인. preoperative라는주석은Full안의그룹을뜻하며Preop모델정확목록을입증하지않음. Full에서7개빼23개라고실제Preop모델목록을확정하지않음. 추후김하연preop결과폴더의feature목록확인필요.
-교수님목록을그대로변수표로옮기지않고Full목록은확인완료표,Preop는보류열로구분. 약어/단위/시점의완전한임상정의는코드이름만으로확정할수없음.
-eGFR는cleaning에서개발데이터0/1을보존하고external>=60을1로코딩하는함수가있으나표시명은≤60으로적힌부분이있음. 새로운전처리를요구하는뜻이아니며,최종변수정의표의표시명은이후원본dictionary/actualfeature정의로확인한뒤기입. 이번CSV는labeldraft임을명시.

## 실제 산출물
-manuscript_updates/Full30_predictor_inventory_20261119.csv:30개이름/코드그룹/Full포함확인,Preop미검증명시. 제출완료표아님.
-manuscript_updates/analysis_set_counts_seed7_notebook_20261119.csv:저장출력의집계. 중복행표시.

## 교수님께 질문할 범위
사용자설명:초안에서는Figure1로환자선정흐름도를고려했으나수정원고수령후삭제됨. 삭제이유를추정하지않고,TRIPOD+AI20a(선정흐름)·21(분석별n/events)에대응한보고방식을여쭙는다. checklist20a는도움이될수있는diagram이라고하며Figure1이라는형식/번호를의무화하지않음.
-기관별최초screenedn,제외사유별n/중복제외우선순위등확인가능자료유무.
-흐름도본문복원vsSupplementary배치vs표/문단대응중선호.
-본문복원시기존Figure1성능→2,기존Figure2SHAP→3이되는안은가능한선택일뿐;지시전번호변경안함.
-Supplementary배치시기존eFigure1/2와최종첫인용순서에따라번호결정. 자동으로eFigure3확정하지않음.
-분할별n/events는기존노트북에서확인되므로새분석요청보다흐름도하단/보충표/Results문단중효율적배치를질문. 제외인원을새로역산하지않음.

## 추가할 메일 문단
“TRIPOD+AI 체크리스트를 정리하면서 환자 선정 과정과 분석군별 환자 수·AL 사건 수의 보고 위치를 함께 점검하고 있습니다. 초안에서는 환자 선정 흐름도를 Figure 1로 고려했으나 전달받은 수정 원고에서는 제외되어 있어, 이를 어떤 형태로 제시하는 것이 좋을지 여쭙고자 합니다. 각 기관의 최초 선별 환자 수와 제외 사유별 인원을 확인할 수 있는 자료가 있다면 공유 또는 확인을 부탁드립니다. 분석군별 환자 수와 사건 수는 기존 노트북에서 확인한 내용을 정리하되, 선정 흐름도를 본문에 다시 포함할지, Supplementary의 그림·표로 제시할지와 기존 표·그림의 순서 및 구성에 대해서도 지도 부탁드립니다.”
