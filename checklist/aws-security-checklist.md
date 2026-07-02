# AWS Security Checklist

| Control ID | Control Area | Security Check | Status | Evidence |
|---|---|---|---|---|
| COST-001 | Cost Control | Monthly AWS Budget created before lab activity | Pass | billing-budget-created.png |
| COST-002 | Cost Control | Budget alert thresholds configured for actual and forecasted cost | Pass | billing-budget-alerts.png |
| IAM-001 | Identity | Root account not used for daily lab activity | Planned | Manual review |
| IAM-002 | Identity | MFA enabled on root account | Planned | Screenshot recommended |
| IAM-003 | Identity | Excessive wildcard IAM policy identified | Fail / Finding Created | iam-insecure-policy-before.png |
| IAM-004 | Identity | Least-privilege IAM policy created | Pass | iam-remediated-policy-after.png |
| IAM-005 | Identity | Least-privilege IAM policy reviewed in Visual editor | Pass | iam-remediated-policy-visual-mode.png |
| IAM-006 | Identity | Insecure wildcard IAM policy deleted after evidence collection | Remediated | iam-insecure-policy-deleted.png |
| S3-001 | Storage | S3 Block Public Access enabled | Pass | s3-block-public-access-after.png |
| S3-002 | Storage | Default encryption enabled on S3 bucket | Pass | s3-encryption-after.png |
| S3-003 | Storage | No real sensitive data uploaded | Pass | sample file note |
| S3-004 | Storage | Fake test files uploaded for lab simulation | Pass | s3-test-files-uploaded.png |
| LOG-001 | Logging | CloudTrail Event History reviewed | Reviewed | cloudtrail-event-history-main.png |
| LOG-002 | Logging | IAM policy event search attempted in CloudTrail | Reviewed | cloudtrail-iam-event-search-no-results.png |
| CSPM-001 | Posture Management | Security Hub findings reviewed | Pass | securityhub-all-findings.png |
| CSPM-002 | Posture Management | High-severity IAM wildcard finding identified | Fail / Finding Created | securityhub-finding-detail.png |
| CSPM-003 | Posture Management | Insecure wildcard IAM policy remediated | Remediated | iam-insecure-policy-deleted.png |
| CSPM-004 | Posture Management | Security Hub summary page reviewed | Pass | securityhub-summary-enabled.png |
| DET-001 | Threat Detection | GuardDuty sample findings reviewed | Planned | guardduty-sample-findings.png |
| CLEAN-001 | Cleanup | Trial services disabled after evidence collection | Planned | cleanup-and-cost-control.md |
