## Security Hub Finding: IAM Wildcard Administrative Privileges

**Severity:** High

**Status:** Remediated

**Finding:**  
Security Hub identified that an IAM customer-managed policy allowed full `"*"` administrative privileges.

**Evidence:**  
Security Hub generated a high-severity finding titled `IAM policies should not allow full "*" administrative privileges`.

**Risk:**  
IAM policies with full wildcard permissions can allow broad administrative access across AWS services and resources. If attached to an identity, this could lead to privilege escalation, unauthorized resource modification, data exposure, account compromise, or unexpected cloud costs.

**Remediation:**  
The intentionally insecure lab policy was removed after evidence collection. A least-privilege replacement policy was created to allow only read-only access to the specific S3 lab bucket.

**Validation:**  
The least-privilege policy was reviewed in IAM and documented in the repository. Security Hub finding evidence was captured before remediation, and the insecure policy was deleted from the AWS account.

**Screenshot Evidence:**  
- `screenshots/securityhub-all-findings.png`
- `screenshots/securityhub-finding-detail.png`
- `screenshots/securityhub-iam-finding-resource.png`
- `screenshots/iam-insecure-policy-before-deletion.png`
- `screenshots/iam-insecure-policy-deleted.png`
- `screenshots/iam-remediated-policy-after.png`
- `screenshots/iam-remediated-policy-visual-mode.png`
