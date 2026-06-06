# PayBridge Access Control Policy

**Version:** 1.0
**Effective Date:** [Today's date]
**Owner:** Security Team
**Review Frequency:** Annual

---

## 1. Purpose

This policy establishes requirements for
controlling logical access to PayBridge
systems, applications and data.

It supports SOC 2 Trust Service Criteria:
CC6.1, CC6.2, CC6.3, CC6.6

---

## 2. Scope

This policy applies to:
→ All PayBridge employees
→ All contractors with system access
→ All third-party vendors with access
→ All PayBridge systems and applications

---

## 3. Access Principles

### 3.1 Least Privilege
Every user receives the minimum access
required to perform their job function.
Access is never granted beyond what is
operationally necessary.

### 3.2 Need to Know
Access to sensitive data is restricted
to individuals with a legitimate
business need.

### 3.3 Separation of Duties
No single individual controls all
aspects of a critical process.
Development and production access
are kept separate.

### 3.4 Default Deny
All access is denied by default.
Access is explicitly granted
only when required.

---

## 4. Access Request Process

### New Employee Onboarding
1. HR notifies Security team
   on employee start date minus 2 days
2. Manager submits access request form
   specifying required systems and role
3. Security team provisions access
   based on role template
4. MFA device registered on Day 1
5. Access confirmed with employee
   on first day

### Contractor and Vendor Access
1. Business owner submits access request
2. Security team reviews scope and duration
3. Minimum access granted for specified period
4. Access reviewed monthly
5. Access revoked on contract end date

---

## 5. Access Review Process

### Quarterly Review
1. Security team exports IAM credential report
2. Cross-reference with current HR employee list
3. Identify any access anomalies:
   → Terminated employees with active access
   → Role changes requiring permission updates
   → Users inactive for 90+ days
   → Access keys older than 90 days
4. Remediate findings within 5 business days
5. Document review completion and findings

### Annual Recertification
All access rights are formally recertified
annually by system owners and managers.

---

## 6. Privileged Access

### Admin Access Requirements
→ Separate privileged account required
→ MFA mandatory — no exceptions
→ Activity logged and reviewed monthly
→ Used only when required
→ Shared admin accounts prohibited

### Root Account (AWS)
→ Used only for emergency recovery
→ MFA enabled at all times
→ Access keys never created
→ All usage immediately reviewed

---

## 7. Offboarding Process

When an employee leaves PayBridge:

**Immediate (same day as departure):**
- [ ] Disable AWS IAM account
- [ ] Revoke all active AWS sessions
- [ ] Remove from all IAM groups
- [ ] Disable GitHub account
- [ ] Remove Okta account
- [ ] Remove MFA devices

**Within 24 hours:**
- [ ] Remove from all SaaS applications
- [ ] Revoke any API keys or tokens
- [ ] Remove from shared credential vaults
- [ ] Review and reassign open tickets

**Within 5 business days:**
- [ ] Confirm all access removed
- [ ] Document completion in offboarding log
- [ ] Manager sign-off obtained

---

## 8. Password Requirements

Minimum length: 14 characters
Complexity: Upper + lower + number + special
Maximum age: 90 days
Password reuse: 24 passwords remembered
MFA: Required for all accounts

---

## 9. Remote Access

→ VPN required for production access
→ MFA required for all remote sessions
→ Session timeout: 30 minutes idle
→ Access logged and reviewable

---

## 10. Exceptions

Exceptions to this policy require:
→ Written request to Security team
→ Business justification documented
→ Compensating controls identified
→ Time-limited approval only
→ Monthly review of all exceptions

---

## 11. Policy Violations

Violations of this policy may result in:
→ Immediate access revocation
→ Disciplinary action
→ Termination for serious violations

---

## Approval

**Approved by:** [CEO Name]
**Date:** [Date]
**Next review:** [Date + 1 year]
