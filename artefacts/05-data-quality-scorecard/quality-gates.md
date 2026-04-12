# Quality Gates

Per-milestone gating thresholds for data migration quality.

## Gate Thresholds

| Milestone | Completeness | Accuracy | Consistency | Validity | Action if Failed |
|---|---|---|---|---|---|
| Initial Profiling | Report only | Report only | Report only | Report only | — |
| Pre-Cleansing | ≥ 80% | ≥ 70% | ≥ 75% | ≥ 70% | Extend cleansing phase |
| Post-Cleansing | ≥ 95% | ≥ 90% | ≥ 95% | ≥ 90% | Re-cleanse failed domains |
| Rehearsal 1 | ≥ 98% | ≥ 95% | ≥ 97% | ≥ 95% | Root cause analysis |
| Rehearsal 2 | ≥ 99% | ≥ 98% | ≥ 99% | ≥ 98% | Escalate to programme lead |
| Go-Live | ≥ 99.5% | ≥ 99% | ≥ 99.5% | ≥ 99% | No-go |

## Gate Process
1. Run profiling on target dataset
2. Calculate metrics per domain
3. Compare against thresholds
4. Record pass/fail in quality-scorecard.md
5. If failed: root cause → remediation → re-profile
