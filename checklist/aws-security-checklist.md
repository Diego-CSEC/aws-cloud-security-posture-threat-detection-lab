# AWS Security Checklist

| Control ID | Control Area | Security Check | Status | Evidence |
|---|---|---|---|---|
| COST-001 | Cost Control | Monthly AWS Budget created before lab activity | Planned | billing-budget-created.png |
| IAM-001 | Identity | Root account not used for daily lab activity | Planned | Manual review |
| IAM-002 | Identity | MFA enabled on root account | Planned | Screenshot recommended |
| IAM-003 | Identity | Excessive wildcard IAM policy identified | Fail / Finding Created | iam-insecure-policy-before.png |
| IAM-004 | Identity | Least-privilege IAM policy created | Pass | iam-remediated-policy-after.png |
| S3-001 | Storage | S3 Block Public Access enabled | Pass | s3-block-public-access-after.png |
| S3-002 | Storage | Default encryption enabled on S3 bucket | Pass | s3-encryption-after.png |
| S3-003 | Storage | No real sensitive data uploaded | Pass | sample file note |
| LOG-001 | Logging | CloudTrail Event History reviewed | Planned | cloudtrail-event-history.png |
| CSPM-001 | Posture Management | Security Hub findings reviewed | Planned | securityhub-findings-before.png |
| DET-001 | Threat Detection | GuardDuty sample findings reviewed | Planned | guardduty-sample-findings.png |
| CLEAN-001 | Cleanup | Trial services disabled after evidence collection | Planned | cleanup-and-cost-control.md |
