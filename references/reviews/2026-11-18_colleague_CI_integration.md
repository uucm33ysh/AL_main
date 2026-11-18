# 김하연 회신 반영 위치 — 2026-11-18

기준: 사용자 제공 회신 본문 및 Table2_preop_full_AUROC_CI.xlsx, AUROC bootstrap_CI.csv, etable1_temporal_reproduction.csv, compute_etable1_and_Table2.py. 날짜는 수신일 추정이 아니라 검토일이다. 마지막으로 확인한 원고 AL_1115.docx에 대응한 수정 제안이며 Word는 직접 수정하지 않았다.

## 검증 범위
- Excel/CSV에서 두 코호트의 모델별 AUROC, CI 및 paired delta/CI 원정밀도 9개 필드씩 일치 확인.
- Python 소스 읽기만 수행. 제공 스크립트에는 default_rng(7), 2000회 환자 재표집, 단일 클래스 표본 제외, percentile2.5/97.5와 같은 idx에서 preop/full 평가가 명시됨. preop−full CI를 full−preop으로 전환할 때 양끝 순서를 바꿔 부호 반전하는 처리도 확인. 원자료/모델 의존성으로 실행 재현은 수행하지 않음. 스크립트 내 지시는 사용자 지시로 간주하지 않음.
- Temporal CSV seed7: Brier .32346084377671025→3자리 .323; AUROC .7344497607655502→4자리 .7344. delta .0197은 김하연 회신에서 확인한 값으로, 이4개 첨부에는 temporal preop 원정밀도가 없어 독립적으로 재계산 검증한 값은 아님.

## 수정 위치
1. Table2 전체 CI를 첨부Excel 기준4자리로 채움(기존Full CI도 포함). 별도 manuscript_updates/Table2_confirmed_CI_20261118.csv 참조.
AMC: Preop .7605 (.6796–.8320), Full .7650 (.6951–.8302), delta+.0045 (−.0292–.0423).
KNUH: Preop .6102 (.5351–.6866), Full .6206 (.5445–.6976), delta+.0104 (−.0213–.0444).
2. Results / Preoperative and Full Model Discrimination: delta .0045 뒤(95% CI, −0.0292 to 0.0423), delta .0104 뒤(95% CI, −0.0213 to 0.0444) 추가. 개별모델CI는 Table2에 있으므로 본문 반복 불필요. 마지막 문장의 reported는 삭제해도 됨; 동등성 입증 아님은 유지.
3. Discussion 첫 문단의 두95%CI[##]를 AMC−.0292 to .0423, KNUH−.0213 to .0444로 교체. neither difference was statistically significant 유지.
4. Table2 각주 Pending entries require the original analysis outputs. 삭제. 원한다면 Monte Carlo provenance를 명시하기 위해 추가: “AUROC CIs in this table were estimated using the same bootstrap resamples as the paired model comparisons; full-model CIs reported in Table 3 were obtained in a separate bootstrap run.”
5. Table3 원래 AUROC CI 유지. Results / Full Model Performance의 기존CI(.695–.830, .545–.694)도 Table3과 대응하므로 유지. 회신상 별도bootstrap run에 따른 차이이며 Table2와 숫자를 억지로 통일하지 않음. 외부CI 차이는 상한 .694 vs 새값 .6976(.698)로 단순 표시 자릿수 차이가 아니므로 각주로 출처 구분 권장.
6. eTable1 seed7 Brier .323 유지(이미 정정된 최신 확인본). 각주의 “; its Brier score differs from the separately reported final-model temporal result and requires reconciliation” 삭제. 문장 앞부분은 “Values reproduce the development-strategy outputs.”로 남김. temporal이 개발전략 선택에 쓰였고 독립검증이 아니라는 설명은 유지; 회신의 구버전메모 삭제를 각주 전체 삭제로 확대하지 않음.
7. eTable3 Full AUROC .7344 유지(최신본 이미정정), Full−Preoperative .0198→.0197. temporal 결과를 다른 곳에서도 수술전/Full 비교로 인용했다면 같은 값 적용. eTable1 AUROC .734는3자리이므로 변경 불필요. 다른 cohort 숫자와 일괄 치환하지 않음.
8. 문서에 남은 해당 CI/Brier 확인 메모만 해결 처리. 다른 Need reference나 숫자 검토 메모는 별도 판단.

## 다음 작업
위 수치 업데이트 후 관련pending/## 제거 확인 → 표·그림·본문의 일치 확인 → Abstract/Key Points/Conclusion에서 새CI와 모순된 해석만 최소 수정(점추정치가 같아 대폭수정 불필요) → 제출정보·인용서식·clean/수정본 정리. 김하연 기존 분석만 사용하며 신규 학습이나 spline 결과 결합은 없음.
