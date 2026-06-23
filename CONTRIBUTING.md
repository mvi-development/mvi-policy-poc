# GitHub 운영 정책 변경 규칙

## 변경 흐름

1. 정책 변경 초안은 Issue로 등록합니다.
2. 문서 또는 템플릿 변경은 Pull Request로 진행합니다.
3. 최소 1명 이상 검토 후 `main`에 반영합니다.

## Free 티어 운영 제약

GitHub Free 조직의 private repository에서는 protected branch와 ruleset을 이용한 강제 통제가 제한됩니다. 이 저장소는 public repository이므로 branch protection 또는 ruleset 적용이 가능합니다. 다만 현재 Codex 커넥터에서는 해당 설정 API가 노출되지 않아, GitHub 웹 설정에서 별도 적용해야 합니다.

권장 public repo 보호 설정:

- `main` branch protection 적용
- pull request required before merging
- 최소 승인 1건
- status check required: `basic-checks`
- force push 금지
- deletion 금지

## 정책 문서 기준

- Free 티어에서 가능한 설정과 유료 티어가 필요한 설정을 분리해서 기록합니다.
- VPN, self-hosted runner, Power Automate Premium, Enterprise SSO는 필요성이 확인된 뒤 별도 검토 항목으로 둡니다.
