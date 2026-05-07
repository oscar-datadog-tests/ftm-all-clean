# QA card — ftm-all-clean

## Description

Zero flakes, all protections on. Drives every "clean" verdict on the page and the §7.3 empty state.

## Audit cells exercised

- §3.4 #7 — "Your CI signal is clean."
- §5.2 #1 — "Prevention is working. No new flaky tests reached your default branch this month."
- §6.2 #1 — "No flaky pipeline failures to mitigate. Turn on Auto Test Retries to recover any future flakes."
- §7.2 #1 — "No active flaky tests in this repository."
- §7.3 — empty state card with success icon and "Last 30 days" footer.

## Required Datadog toggles

| Toggle | State | Notes |
| --- | --- | --- |
| EFD | **on** | Repo settings |
| PR Gate | **on** | Source Code rule scoping this repo |
| ATR | **on** | Repo settings |
| Policies | **full** | Default 7-day quarantine policy on |

## Special setup steps

None.

## Expected verdicts (after warm-up)

- §3.4 next-action: "Your CI signal is clean."
- §5.2 prevention verdict: "Prevention is working. No new flaky tests..."
- §6.2 mitigation verdict: "No flaky pipeline failures to mitigate..."
- §7.2 remediation verdict: "No active flaky tests in this repository."

## Readiness

T+7.

## How to refresh

```bash
git commit --allow-empty -m "rerun" && git push
```
