# AWS Cloud Security Assessment Report

## 1. Assessment Overview

This report documents a simulated AWS cloud security assessment focused on identity access, storage security, audit visibility, cloud security posture management, threat detection readiness, and cost control.

The lab was designed to simulate a small organization that recently started using AWS and needed a security review of common cloud misconfigurations. The assessment included manual review, AWS-native security tooling, screenshots, remediation steps, and cleanup planning.

## 2. Lab Environment

| Item | Details |
|---|---|
| Cloud Provider | Amazon Web Services |
| Primary Region | `us-east-2` / United States (Ohio) |
| Project Type | Cloud Security Portfolio Lab |
| Data Used | Fake lab data only |
| Main Services Reviewed | IAM, S3, CloudTrail Event History, AWS Budgets, Security Hub, GuardDuty |
| Trial Services Used | AWS Security Hub free trial, Amazon GuardDuty free trial |
| Services Avoided for Cost Control | EC2, RDS, NAT Gateway, Load Balancers, CloudTrail Lake, Macie, Inspector, Detective |

## 3. Assessment Scope

The assessment reviewed the following areas:

- AWS cost-control configuration
- IAM policy risk
- Least-privilege remediation
- S3 bucket public access controls
- S3 encryption settings
- CloudTrail Event History visibility
- Security Hub posture management findings
- GuardDuty threat detection findings
- Root account usage risk
- Cleanup and free-trial tracking

The following services were intentionally excluded from this phase of the lab to reduce cost and complexity:

- Amazon EC2
- Amazon RDS
- NAT Gateway
- Elastic Load Balancing
- Amazon Macie
- Amazon Inspector
- Amazon Detective
- CloudTrail Lake
- VPC Flow Logs
- Customer-managed KMS keys

## 4. Methodology

The assessment followed a basic cloud security review workflow:

1. Configure cost-control guardrails before creating lab resources.
2. Create an intentionally insecure IAM policy to simulate excessive permissions.
3. Create an S3 bucket with fake lab files.
4. Validate S3 public access controls and encryption.
5. Create a least-privilege IAM policy scoped to the specific S3 bucket.
6. Review CloudTrail Event History for AWS management activity.
7. Enable AWS Security Hub to review posture management findings.
8. Document Security Hub findings, risks, remediation steps, and screenshot evidence.
9. Remove the intentionally insecure IAM policy after evidence collection.
10. Enable Amazon GuardDuty to review threat detection findings.
11. Review GuardDuty root credential usage finding.
12. Begin remediation by creating an IAM administrative user for future daily lab activity.
13. Track cleanup actions to avoid unnecessary AWS charges.

## 5. Findings Summary

| ID | Severity | Finding | Source | Status |
|---|---|---|---|---|
| COST-001 | Low | AWS Budget alert was needed before enabling lab resources | AWS Budgets | Remediated |
| IAM-001 | High | IAM policy allowed full wildcard administrative privileges | Manual IAM Review / Security Hub | Remediated |
| IAM-002 | Medium | Root account was used for daily lab activity | GuardDuty / Manual IAM Review | Remediation In Progress |
| S3-001 | Medium | S3 public access controls required validation | Manual S3 Review | Pass |
| S3-002 | Medium | S3 default encryption required validation | Manual S3 Review | Pass |
| LOG-001 | Low | CloudTrail Event History review was needed for audit visibility | CloudTrail Event History | Reviewed |
| CSPM-001 | Informational | Security Hub findings were reviewed for posture management | AWS Security Hub | Reviewed |
| DET-001 | Informational | GuardDuty findings were reviewed for threat detection workflow | Amazon GuardDuty | Reviewed |

---

# COST-001: AWS Budget Alert Configuration

**Severity:** Low  
**Status:** Remediated  
**Source:** AWS Budgets

## Description

A monthly AWS Budget was configured before enabling lab resources and free-trial security services.

## Why This Matters

Cloud security is not only about preventing unauthorized access. It also includes preventing financial risk caused by misconfigured or forgotten cloud resources.

Unexpected cloud costs can occur when users accidentally enable paid services, deploy resources in multiple Regions, or forget to disable trial services.

## Risk

Without budget alerts, unexpected AWS charges may go unnoticed until the end of the billing cycle.

## Remediation

A monthly AWS Budget was created with alert thresholds to notify the account owner if costs approached the configured limit.

Configured budget controls:

- Monthly budget amount: `$1.00`
- Actual cost alert: `50%`
- Forecasted cost alert: `80%`
- Email notification enabled

## Validation

Budget alert configuration was reviewed and documented with screenshot evidence.

## Screenshot Evidence

- `screenshots/billing-budget-created.png`
- `screenshots/billing-budget-alerts.png`

---

# IAM-001: Excessive IAM Wildcard Permissions

**Severity:** High  
**Status:** Remediated  
**Source:** Manual IAM Review / AWS Security Hub

## Description

An intentionally insecure IAM customer-managed policy was created as part of the lab to simulate excessive administrative permissions.

The policy allowed full wildcard access:

```json
{
  "Effect": "Allow",
  "Action": "*",
  "Resource": "*"
}
