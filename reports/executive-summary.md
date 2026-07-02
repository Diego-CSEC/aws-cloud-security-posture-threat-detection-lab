# Executive Summary

This project documents a simulated AWS cloud security assessment focused on identity access, storage security, audit visibility, threat detection, and cost control.

The assessment reviews common cloud security risks including excessive IAM permissions, S3 bucket exposure, missing validation of encryption controls, limited audit visibility, and the need for billing safeguards before enabling cloud security tools.

The lab uses AWS IAM, Amazon S3, CloudTrail Event History, AWS Budgets, Security Hub CSPM, and GuardDuty to simulate a realistic Cloud Security Analyst workflow.

The most significant planned finding is an intentionally insecure IAM policy allowing wildcard access to all AWS actions and resources. This finding will be remediated by creating a least-privilege S3 read-only policy scoped to a specific lab bucket.

The final deliverable will include screenshots, risk ratings, remediation steps, security checklist results, Security Hub findings, GuardDuty sample findings, and cleanup documentation.
