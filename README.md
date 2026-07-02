# AWS Cloud Security Posture & Threat Detection Lab

## Overview

This project is a hands-on AWS cloud security portfolio lab focused on identifying, documenting, and remediating common cloud security risks.

The lab simulates a small organization that recently started using AWS and needs a security review of identity access, storage security, audit visibility, threat detection, and cost controls.

## Project Goals

- Build a realistic cloud security assessment lab.
- Identify insecure IAM permissions.
- Apply least-privilege access controls.
- Secure an Amazon S3 bucket.
- Review AWS CloudTrail Event History.
- Use AWS Security Hub CSPM during a free trial.
- Use Amazon GuardDuty during a free trial.
- Document findings, remediation steps, screenshots, and cleanup actions.
- Create a project that can be shown to recruiters for Cloud Security Analyst roles.

## Skills Demonstrated

- AWS Identity and Access Management security review
- IAM policy analysis
- Least-privilege remediation
- S3 bucket security assessment
- CloudTrail event review
- Security Hub CSPM findings review
- GuardDuty threat detection workflow
- Security documentation and reporting
- Cost control and cloud cleanup

## AWS Services Used

- AWS IAM
- Amazon S3
- AWS CloudTrail Event History
- AWS Budgets
- AWS Security Hub CSPM
- Amazon GuardDuty

## Services Intentionally Avoided

To reduce cost risk, this lab does not use:

- EC2
- RDS
- NAT Gateway
- Load Balancers
- AWS Config beyond what Security Hub may require
- CloudTrail Lake
- VPC Flow Logs
- Customer-managed KMS keys
- Amazon Macie
- Amazon Inspector
- Amazon Detective

## Region Used

All resources are created in:

`us-east-1`

Using one Region keeps the lab easier to manage, easier to document, and safer for cost control.

## Project Deliverables

- Security assessment report
- Executive summary
- IAM policy examples
- Before-and-after screenshots
- S3 security validation
- CloudTrail event review
- Security Hub findings review
- GuardDuty sample finding review
- Cleanup and cost-control documentation

## Free Trial Tracking

| Service | Region | Trial Start Date | Planned Disable Date | Status |
|---|---|---|---|---|
| Security Hub CSPM | us-east-1 | TBD | TBD | Not started |
| GuardDuty | us-east-1 | TBD | TBD | Not started |

## Findings Summary

| ID | Severity | Finding | Source | Status |
|---|---|---|---|---|
| IAM-001 | High | Excessive IAM wildcard permissions | Manual IAM Review | Planned |
| S3-001 | Medium | S3 public access controls require validation | Manual Review / Security Hub | Planned |
| S3-002 | Medium | S3 encryption requires validation | Manual Review / Security Hub | Planned |
| LOG-001 | Low | CloudTrail Event History review needed | CloudTrail | Planned |
| DET-001 | Informational | GuardDuty sample findings review | GuardDuty | Planned |
| COST-001 | Low | Budget alert needed before enabling trial services | AWS Budgets | Planned |

## Cost Control

This lab uses AWS Budgets, one AWS Region, minimal resources, and cleanup documentation to reduce the risk of unexpected charges.

Security Hub and GuardDuty are only used during free-trial testing and will be disabled after screenshots and findings are documented.
