# 작업 이력 — 시간순

기준 시간대: Asia/Seoul. 아래 과거 이력은 2026-11-17에 기존 대화와 산출물을 바탕으로 재구성했습니다. 날짜가 불명확한 세부 작업에는 임의 시각을 부여하지 않았습니다. 메일의 연구 이력과 현재 원고 편집 작업을 구분합니다.

| 날짜 | 작업/결정 | 상태·후속 작업 |
|---|---|---|
| 2026-11-05 | Colab 노트북·원자료를 검토하고 환경을 준비. 별도 탐색 분석도 수행 | 현재 논문은 김하연 결과만 사용. 별도 spline 및 assistant 재학습 산출물은 인용/수치 대체에서 제외 |
| 2026-11-12 | 교수님의 11/11 지도를 기준으로 새 모델 확장보다 기존 연구 마무리에 집중 | 전처리 재검토는 현재 작성 업무에서 제외. 미확인 방법을 문헌/메일로 추정하지 않음 |
| 2026-11-13 | AL_1113 중간본 검토. 기관별·통합 분석의 Methods/Results 추가 및 Supplementary 구성 논의 | 본문 Figure1/2, 보충 eFigure1/2 유지 |
| 2026-11-15 | eFigure/표 legend·약어, 최소 Discussion 수정, prospective future work 정리 | 수술자/tension/혈류/출혈량 및 장루·모니터링의 전향적 평가를 후속 방향으로 반영 |
| 2026-11-15 | KNUH baseline Colab 노트북 게시, 사용자 실행 산출물 대조 | Table1 KNUH781명/AL62건 등 채움. CSV/Excel 일치 확인 |
| 2026-11-15 | 업로드된 validation CSV와 저장 예측확률을 대조 | seed7 Brier .3234608… → .323. 별도 final temporal Brier의 출처는 확인 대기 |
| 2026-11-15 | CI·temporal 결과 확인 요청 메일 문안 준비 | 발송/회신 완료로 간주하지 않음. Table2 CI4개 및 Discussion 대응 빈칸 대기 |
| 2026-11-17 | 기존 문헌 PDF 및 REAL/EssentiAL 원문 검토. 인용 추적 방식으로 확대 | geography/volume/숙련도를 구분하고 원문 직접 근거 탐색 |
| 2026-11-17 | REAL·Sakamoto 참고문헌을 거쳐 Xu/Zhao/COLRAR 원문 확인 | Intro supporting reference로 COLRAR 우선, Zhao 보조. 인과/지역 우월성 주장 아님 |
| 2026-11-17 | AL.enl 및 AL_1115.docx 점검, Park/Zhao 수정용 RIS 준비 | 원문 문헌2개 존재하나 서지정보 보완·Riley/Collins 추가 여부·Word 연결 필요 |
| 2026-11-17 | 사용자 요청으로 RIS·근거표·작업 기록을 GitHub 관리 구조로 정리 | [일별 상세 기록](worklogs/2026-11-17.md) 참조 |

다음 세션의 시작점은 [STATUS](STATUS.md)입니다.

- 2026-11-17 추가 업로드 AL_1115.docx 인용 재검토: EndNote 연결 및 Park/Zhao DOI 반영 확인. 수기/자동 참고문헌 중복, Methods TRIPOD 번호, 저널/DOI 필드 오류를 별도 점검 기록으로 남김. 원고 원본은 변경하지 않음.

- 2026-11-17 Ochs PDF 원문 대조: 9120명/34개/F1 .87→.70 확인. 실제 변수 목록의 수술 관련 항목 때문에 엄격한 preop-only 인용은 제한; 두 문장 최소 수정 제안과 11/18 작업 순서를 기록.

- 2026-11-18 Discussion high-volume 문단: COLRAR PDF2쪽 표준화/quality control 근거 재확인. 문단 기능을 유지하는 최소 수정안과13번 인용 위치 기록(원고 미적용, 논의 중).

- 2026-11-18 김하연 회신4파일 검토. Table2 Excel/CSV 원값 일치, CI 반영 위치와 eTable1 구버전 메모 삭제/eTable3 delta .0197 정정 기록. Table3 및 대응Results의 기존 bootstrap CI 유지. Word 미적용.

- 2026-11-18 최신 AL_1117.docx 전체 점검. 실제 남은AUROCCI문장/Table2수치차이, Table3AUROC없음 정정확인. 회신반영완료와9개11pt혼재구간/표기오류/참고문헌/제출정보작업 분리. 이미지4개직접확인. Word원본미변경,렌더링미검증. docs/reviews/2026-11-18_AL_1117_review.md 참조.

- 2026-11-18 AL_new.enlx 압축/내부문자열점검. Park/Zhao DOI,Frye저자보완확인; %J DOI잔재/저널/Pages보완필요. AL_1117 Frye/Park필드는다른libraryID인점기록. Native앱갱신미검증,원본미변경.

- 2026-11-18 사용자 명시 요청으로 새 업로드 AL_1118.docx와 AL_new.enlx를 manuscript_versions/2026-11-18/에 원본 보관. ZIP CRC 및 SHA-256 복사동일성 확인. 내용수정/연결검증 없음. manifest와최신위치기록.

- 2026-11-19 AL_1118재업로드는11/18보관본과동일확인. CI본문/표일치및본문12pt·수기목록삭제완료확인. .019 7/indㄹependent/Table1각주잔재등남은교정기록. 원고미수정,EndNote작업보류.

- 같은점검내재확인: Table셀의run을공백없이이어읽으면eTable3 .0197및AMCFull괄호가정상. 앞서추출과정에서인위적으로생긴공백지적철회. 최신리포트정정.

- 2026-11-19 AL_1119에서Discussion경북대메모/Table1 unknown MRF22.9·EMVI21.8확인,eTable1각주유지권장. 취소선/수정색정리본을첨부할전제의회람메일초안저장. EndNote/ref완료목표11/24(화). 미발송,원고미변경;업로드파일은아직표시본.

- 2026-11-19 회람용두원고/TRIPOD+AI템플릿검토. 정리본일부색/취소선잔재및KNUH미병기확인. 체크리스트페이지란미작성. 보고항목매핑/기존자료보완/연구진확인/제출패키지단계계획저장. 원고원본미수정,추가분석자동요구안함.

- 2026-11-19 신규노트북ZIP검토. Full30목록및seed7분할별AL70/24/24저장출력확인;Preop전용목록은미포함. predictorinventory/집계저장. 초안Figure1삭제경위는추정하지않고선정제외수·표현형식/번호질문문안정리. 재학습/전처리변경없음.
