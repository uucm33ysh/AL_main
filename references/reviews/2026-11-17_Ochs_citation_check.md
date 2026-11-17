# Ochs 원문–본문 인용 연결 점검 및 다음 작업

기준일: 2026-11-17 (Asia/Seoul). 최신 업로드 AL_1115.docx와 Ochs et al. JAMA Network Open 2025;8(10):e2538267, doi:10.1001/jamanetworkopen.2025.38267 원문을 대조. PDF 첨부 ID file_000000003a8c820e9ae6091ec3e6ce46. 원고는 변경하지 않음.

## 확인
- 새 원고 번호8은 Ochs. Introduction ML 문단, Discussion 첫 finding 설명, reverse-direction 해석 문단에서 연결 확인.
- PDF1,5쪽: 총9120명, 13개 기관6079명 + ESCP3041명. 대상 colon resection with anastomosis. 본 연구의 직장암/비장루 환자군과 같지 않음.
- PDF3쪽 Model Development: “Recorded variables included 34 preoperative risk factors”. 하지만 실제 목록에 type of surgery, surgical approach, anastomotic technique, conversion to open, surgeon’s experience, diverting ostomy, type/configuration of anastomosis 포함. 원문 자체의 preoperative 명칭을 그대로 사용하더라도 엄격한 preoperative-only 모델이라는 근거로 확장하면 안 됨. 계획/실제 시점의 상세 정의는 이 본문만으로 확정하지 않음.
- PDF7쪽 Table1 meta-model F1 cross-validation .87 (95% CI .78–.95), external .70. 원고의87%→70%와 일치. AUROC 차이와 직접 수치 비교하지 않음. 원문의 cross-validation fold 서술에 차이가 있으므로 이 인용에 fold수 추가 불필요.
- PDF9쪽 Limitations는 preoperative features라는 서술과 함께 operative time, blood loss, hypothermia, vasopressors, fluids, anastomotic tension의 후속 평가를 제안. 현재 원고의 장래 intraop 데이터 확장 취지와 관련되지만, 현재 연구의 intraop 추가 이득 부재나 특정 기관 효과를 입증하지는 않음.

## 최소 수정 제안
1. Introduction: “Some use preoperative predictors only. For example, a recent multicenter study of 9120 patients undergoing colon resection used 34 preoperative risk factors, and its F1 score decreased from 87% in cross-validation to 70% in external validation.”의 두 문장을 다음으로 교체 권장:
“For example, a recent multicenter study of 9120 patients undergoing colon resection used 34 clinical predictors and reported F1 scores of 87% in cross-validation and 70% in external validation.” (8번 인용 유지)
엄격한 preoperative-only 예시 역할은 제거. 원고 앞뒤 논리상 해당 예시 유지 가능.
2. Discussion: “The findings are compatible with building models such as that of Ochs et al on preoperative predictors in this setting, but they do not show that preoperative-only models are sufficient elsewhere.”에서 Ochs를 preoperative-only 근거로 연결하는 부분을 제거:
“The findings support further evaluation of preoperative predictors in this setting, but they do not show that preoperative-only models are sufficient elsewhere.”
이 문장은 자체 결과 해석이므로 해당 위치 Ochs8 인용은 제거. Ochs 인용은 Introduction 및 별도 transfer 문단에 유지.
3. Discussion reverse-direction 문단: 다른 모집단/지표/변수를 명시하면서 multicenter colon 모델의 외부 성능 저하를 기술하는 현재 문장과8번 연결은 적절. 수정 불필요.

## 2026-11-18 재개 순서
1. 위 두 문장만 사용자와 확정 후 Word 작업본에 반영; Discussion의 성능 저하 비교 문장 유지.
2. Methods TRIPOD+AI가 새 번호11(Collins)에 연결되는지 수정/확인; 다른 번호는 새16개 체계를 유지. 사용자는 수기/자동 목록 및 EndNote 서식 정리보다 번호/인용 내용 적절성을 이번 우선 범위로 지정.
3. Discussion High-volume surgical practice / Need reference 문단의 각 문장을 근거/가설/자체 결과로 나누어 최소 수정 논의. Park/Zhao의 수술자 경험 근거를 intraop 기여나 아시아 대표성 근거로 확대하지 않음.
4. 김하연 확인 대기 항목 정리: Table2 Preop AUROC CI2개 및 paired delta CI2개; eTable1 final temporal Brier 비교 대상; eTable3 temporal 수치/실행 일치. 회신 전 추정 입력 금지.
5. 반영된 결과에 맞춰 표·그림·eFigure 인용/legend 및 Abstract/Key Points/Conclusion의 명확한 모순만 확인. 교수님 문안 최소 수정, 새 모델/전처리/spline 작업 제외.
6. IRB/저자·교신 정보/분량 등 제출 빈칸 확인 후, 별도 서식 정리와 clean/수정 표시본·변경요약 준비, 초안 회람.
