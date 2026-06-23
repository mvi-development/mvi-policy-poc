# GitHub Free 티어 적용 범위와 보류 항목

## 기준

이 PoC는 GitHub Free 조직에서 가능한 범위 안에서 소스 관리와 Issue Tracking을 먼저 정비합니다. 장기 계약, 신규 장비, 유료 라이선스, 전사 계정 체계 변경은 PoC 결과와 운영 필요성을 확인한 뒤 별도 품의로 진행합니다.

## Free 티어에서 적용

- GitHub Organization 기준 운영
- unlimited public repositories
- unlimited private repositories with limited feature set
- Team access controls
- GitHub Issues
- Pull Request 템플릿
- Issue Forms
- GitHub Actions 2,000 minutes/month

## Free 티어 private repository 제약

GitHub Free와 GitHub Free for organizations에서 Protected Branch와 Rulesets는 public repository에 사용할 수 있습니다. private repository에서 Protected Branch 또는 Rulesets로 PR 승인, required checks, direct push 제한을 강제하려면 GitHub Pro, Team, Enterprise Cloud 또는 Enterprise Server가 필요합니다.

따라서 private repository에서는 다음 항목을 운영 규칙으로 관리합니다.

- `main` 직접 push 금지
- PR 승인 1건 이상
- 관련 Issue 번호 기록
- 기본 검사 실패 시 merge 보류
- 관리자 승인 없는 force push 금지

## public repository 권장 설정

`mvi-policy-poc`는 public repository이므로 GitHub 웹 설정에서 다음 보호 규칙을 적용할 수 있습니다.

- 대상 branch: `main`
- Require a pull request before merging
- Required approvals: 1
- Require status checks to pass before merging: `basic-checks`
- Block force pushes
- Block deletions

## 보류 항목

| 항목 | 보류 사유 | 재검토 조건 |
| --- | --- | --- |
| GitHub Team | 유료 사용자 과금 발생 | private repo branch protection 강제가 필요할 때 |
| Enterprise Cloud / SSO | 전사 계정 체계 변경 필요 | Entra ID SSO와 감사 요건이 확정될 때 |
| Power Automate Premium | 1차 범위 제외 | 표준 커넥터 또는 스크립트로 불가할 때 |
| self-hosted runner | 전용 VM 또는 장비 필요 | GitHub-hosted runner로 빌드가 불가할 때 |
| VPN Gateway | 네트워크 장비와 회선 검토 필요 | 지사 간 내부 자원 공유가 필수일 때 |

## 의사결정 필요 사항

- [ ] Organization 명칭 확정
- [ ] Owner 2명 지정
- [ ] 이관 대상 저장소 목록 확정
- [ ] 개발/QA/CS 연동 계정 권한표 확정
- [ ] CS 원천 저장 위치 확인
