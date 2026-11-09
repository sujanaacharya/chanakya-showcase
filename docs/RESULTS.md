# Results

Numbers only. All of the labeled-set numbers are on code I developed against. They are not estimates of performance on unseen code.

## Labeled set: access control (third-party apps)

| Measure | Value |
|---|---|
| Scored cases | 99 |
| True positives | 53 |
| False positives | 21 |
| False negatives | 4 |
| Precision | 71.62% |
| Recall | 92.98% |
| Confident decisions | 78 of 99 (78.79%) |
| Safe cases marked uncertain | 13 |
| Safe cases not analyzed | 8 |

## Labeled set: other categories

| Set | Scored cases | TP | FP | FN | Precision | Recall |
|---|---:|---:|---:|---:|---:|---:|
| SQL injection, third-party apps | 11 | 8 | 0 | 0 | 100.00% | 100.00% |
| Unsafe deserialization, third-party apps | 11 | 4 | 0 | 2 | 100.00% | 66.67% |

## OWASP Benchmark Java, SQL injection

| Measure | Value |
|---|---|
| Labeled SQL injection cases | 504 |
| Vulnerable cases found | 241 of 272 (88.60%) |
| Precision | 100.00% |
| Confident decision coverage | 241 of 504 (47.82%) |

## IWA-Java, every operation labeled (hardest test)

| Measure | Value |
|---|---|
| Operations | 116 |
| TP / FP / FN | 4 / 25 / 2 |
| Precision | 13.79% |
| Confident recall | 66.67% |

## Real open-source projects

| Measure | Value |
|---|---|
| Confirmed access-control bugs | 4 |
| Of those, matching an already public CVE | 1 (CVE-2026-89261, mogu_blog_v2) |
| Of those, in a project used during development | 1 |
| Last pre-registered round: projects selected | 5 |
| Last pre-registered round: truly unseen projects | 4 |
| Last pre-registered round: confirmed bugs | 0 |

## AI experiments

| Experiment | Result |
|---|---|
| Three-setup comparison (5 cases, 15 runs) | 15 of 15 unresolved |
| AI review of uncertain findings | 62 of 62 completed investigations abstained (31 of 39 cases per arm completed before the run was stopped) |
