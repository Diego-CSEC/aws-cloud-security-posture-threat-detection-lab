# AWS Cloud Security Assessment Report

## 1. Assessment Overview

This report documents a cloud security assessment of a simulated AWS environment. The assessment focuses on identity access, storage security, audit visibility, threat detection, and cost control.

## 2. Scope

Services reviewed: 

- AWS IAM
- Amazon S3
- AWS CloudTrail Event History
- AWS Budgets
- AWS Security Hub CSPM
- Amazon GuardDuty

## 3. Finding: IAM-001 Excessive IAM Permissions

**Severity:** High

**Status:** Remediated

**Description:**  
An IAM policy was created with wildcard permissions for both actions and resources.

**Evidence:**  
The policy includes `"Action": "*"` and `"Resource": "*"`, which grants broad access across AWS services and resources.

**Risk:**  
If attached to a user, group, or role, this policy could allow unauthorized access, privilege escalation, resource modification, data exposure, or full account compromise.

**Remediation Plan:**  
Replace wildcard permissions with a least-privilege policy scoped only to the required service and resource.

**Screenshot Evidence:**  
- `screenshots/iam-insecure-policy-before.png`
- `screenshots/iam-insecure-policy-validation.png`
