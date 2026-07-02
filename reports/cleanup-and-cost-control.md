# Cleanup and Cost Control

## Purpose

This project uses selected AWS free-trial security services to simulate a realistic cloud security analyst workflow. To avoid unnecessary charges, the environment will be reviewed and cleaned up after evidence collection.

## Cost-Control Strategy

- Use one AWS Region: `us-east-1`
- Create AWS Budget alerts before enabling trial services
- Avoid EC2, RDS, NAT Gateway, Load Balancers, CloudTrail Lake, Macie, Inspector, and Detective
- Use fake test data only
- Disable free-trial services after screenshots and findings are documented
- Delete unnecessary test resources after the lab

## Services Reviewed for Cleanup

| Service | Planned Action |
|---|---|
| Security Hub | Disable after screenshots and findings review |
| GuardDuty | Disable after screenshots and sample finding review |
| S3 | Delete fake test files after documentation |
| IAM | Delete intentionally insecure lab policy |
| IAM | Keep remediated policy JSON in GitHub only |
| AWS Budgets | Keep budget active for cost monitoring |
| CloudTrail Event History | No cleanup required |

## Cleanup Validation Checklist

| Check | Status |
|---|---|
| Security Hub disabled | Planned |
| GuardDuty disabled | Planned |
| No EC2 instances created | Planned |
| No RDS databases created | Planned |
| No NAT Gateways created | Planned |
| No CloudTrail Lake event data stores created | Planned |
| No customer-managed KMS keys created | Planned |
| S3 test data removed | Planned |
| Billing dashboard reviewed | Planned |
