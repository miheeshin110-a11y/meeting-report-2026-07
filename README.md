# 2026년 7월 회의 운영 월말 보고서

GitHub Pages 배포용 정적 HTML 보고서입니다.

- 메인 파일: `index.html`
- 원본 문서: `C:/Users/user/Documents/KPI회의/outputs/2026-07_회의운영_월말보고서_v3_보강본.md`

## 경영회의자료 검토 보고서

- 고정 제출 대상: 제품팀, 미디어커머스, 이커머스, 글로벌, 유통사업
- 과거 기준 보고서: `kpi-260902-review.html`, `kpi-260907-review.html`
- 9월 14일 종합 검토 보고서: `kpi-260914-review.html`
- 새 보고서 템플릿: `kpi-report-template.html`
- 작성 규칙: `AGENTS.md`
- 새 보고서 파일명: `kpi-YYMMDD-review.html`

## Slack 자동 공유

- 공유할 보고서는 `latest-report.json`에 지정합니다.
- `status`가 `final` 또는 `demo`일 때만 Slack으로 전송됩니다.
- 초안은 `latest-report.json`을 변경하지 않으므로 자동 공유되지 않습니다.
- 자료 미제출 팀은 `not_submitted_teams`, 수치 미갱신 팀은 `stale_data_teams`, 부분 업데이트 팀은 `not_updated_teams` 배열에 적습니다.
- Slack에는 각각 `팀명 자료 미제출`, `팀명 수치 업데이트 안됨`, `팀명 자료 업데이트 안됨`으로 구분해 표시됩니다.
- Slack 웹훅은 저장소 Actions Secret `SLACK_WEBHOOK_URL`에만 보관합니다.
- 메타데이터만 정정하고 Slack을 보내지 않을 때는 커밋 메시지에 `[skip-slack]`을 포함합니다.

최종 발송 메타데이터 예시:

```json
{
  "report": "kpi-YYMMDD-review.html",
  "title": "YYYY년 M월 D일 경영회의자료 검토",
  "summary": "보고서 핵심 결론",
  "status": "final",
  "not_submitted_teams": ["미디어커머스"],
  "stale_data_teams": ["이커머스"],
  "not_updated_teams": []
}
```

새 보고서는 Google Drive의 최신 회의자료와 회의록, 직전 회차 자료, 저장소의 과거 검토 보고서를 모두 대조해 작성합니다. 모든 정량 KPI는 최소 전전·직전·현재 3개 시점을 비교해 실제 수치 갱신 여부를 확인합니다. 팀별로 `수치 업데이트·주요 변화 → 반영 여부 → 점검 → 우선 조치` 순서로 구분하고, 글꼴과 정렬은 기존 보고서 디자인을 유지합니다.

Drive 폴더 주소는 공개 저장소에 올리지 않고 `.codex/kpi-report-source.local.md`에 로컬로 보관합니다.

