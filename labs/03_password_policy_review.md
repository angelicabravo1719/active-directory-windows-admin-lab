# Lab 03 — Password Policy Review

## Goal

Understand how Windows password policies help protect user accounts from unauthorized access.

Password policies define requirements such as password length, expiration, lockout thresholds, and password history. These controls help reduce the risk of brute-force attacks, credential abuse, and weak password usage.

---

## What I Did

* Reviewed the local Windows password policy using PowerShell.
* Examined password age requirements.
* Reviewed password history settings.
* Analyzed account lockout controls.
* Evaluated the overall strength of the configured password policy.
* Identified potential security risks and improvement opportunities.

---

## Tools Used

### Windows PowerShell

Used to review account and password policy settings.

---

## Commands Used

### Review Password Policy

```powershell
net accounts
```

Displays password requirements, account lockout settings, and other local account security controls.

---

## What I Observed

Windows maintains password and account lockout policies that help regulate authentication security.

The workstation was configured with password expiration and account lockout protections, but several password policy settings were not enforced.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-03-password-policy-review/
```

Files:

```text
password_policy_review.png
```

---

## Investigation Findings

### Password Age Settings

The following password age settings were identified:

```text
Minimum Password Age: 0 days
Maximum Password Age: 42 days
```

#### Observations

* Users can change their password immediately after creating or changing it.
* Passwords are configured to expire every 42 days.

---

### Password Length Requirements

The following setting was identified:

```text
Minimum Password Length: 0
```

#### Observation

* No minimum password length requirement was configured.

This increases the risk of weak passwords being used.

---

### Password History

The following setting was identified:

```text
Password History Maintained: None
```

#### Observation

* Previous passwords are not remembered.
* Users could potentially reuse old passwords after changing them.

---

### Account Lockout Controls

The following lockout settings were identified:

```text
Lockout Threshold: 10
Lockout Duration: 10 minutes
Lockout Observation Window: 10 minutes
```

#### Observations

* An account becomes locked after 10 failed login attempts.
* The lockout remains active for 10 minutes.
* Failed login attempts are tracked within a 10-minute observation window.

These settings help reduce the effectiveness of brute-force password attacks.

---

### System Role

The workstation reported the following role:

```text
WORKSTATION
```

This indicates the device is operating as a local Windows workstation rather than a domain controller.

---

## Security Analysis

Password policies are a foundational component of identity and access management.

Several positive controls were identified:

* Password expiration enforced after 42 days.
* Account lockout protection enabled.
* Failed authentication attempts monitored.

However, several weaknesses were also observed:

* No minimum password length requirement.
* No password history enforcement.
* Users could potentially reuse weak passwords.

In an enterprise environment, stronger password policies would typically be recommended.

---

## Security Relevance

Security analysts frequently review password policies when assessing:

* Authentication security
* Identity and access management
* Compliance requirements
* Brute-force attack resistance
* Account compromise investigations

Weak password policies increase the likelihood of unauthorized access and credential-based attacks.

---

## Key Takeaways

* Password policies help protect user accounts from unauthorized access.
* Account lockout controls reduce brute-force attack effectiveness.
* Password expiration encourages periodic credential changes.
* Password history prevents password reuse.
* Strong password requirements improve overall security posture.

---

## Conclusion

This lab demonstrated how Windows manages password and account security through local password policies. Reviewing password age requirements, lockout controls, and password history settings provided practical experience with authentication security concepts commonly encountered in enterprise environments.

---

## Note

This lab was performed in a personal lab environment for educational and portfolio development purposes.
