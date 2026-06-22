# Lab 04 — Group Policy Basics

## Goal

Understand how Windows Group Policy is used to manage security settings, user configurations, and system behavior.

Group Policy is a Windows administrative framework that allows organizations to centrally manage computers and user accounts. Reviewing Group Policy settings helps administrators understand how security controls and configuration settings are applied across systems.

---

## What I Did

* Attempted to access the Local Group Policy Editor.
* Verified that the Group Policy Editor was unavailable on the installed Windows edition.
* Used PowerShell to review Group Policy processing results.
* Examined applied Group Policy Objects (GPOs).
* Reviewed workstation configuration information.
* Analyzed security group memberships associated with policy processing.

---

## Tools Used

### Windows PowerShell

Used to review Group Policy processing information.

---

## Commands Used

### Review Group Policy Results

```powershell
gpresult /r
```

Displays Resultant Set of Policy (RSoP) information, including applied Group Policy Objects, workstation details, and security group memberships.

---

## What I Observed

The workstation was operating as a standalone Windows system and was not joined to an Active Directory domain.

Group Policy information was processed locally, and no domain-based Group Policy Objects were applied.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-04-group-policy-basics/
```

Files:

```text
group_policy_results.png
```

---

## Investigation Findings

### Local Group Policy Editor Availability

An attempt was made to launch:

```text
gpedit.msc
```

The Local Group Policy Editor was unavailable on the installed edition of Windows.

This is expected on many Windows Home editions where advanced administrative tools are not included by default.

---

### Workstation Configuration

The system reported:

```text
OS Configuration: Standalone Workstation
OS Version: 10.0.26100
```

#### Observations

* The workstation is not joined to an Active Directory domain.
* Policies are managed locally rather than through a domain controller.
* The system operates as an independent Windows workstation.

---

### Group Policy Processing

The system reported:

```text
Domain Type: <Local Computer>
```

#### Observation

* Policy processing occurred locally on the workstation.
* No enterprise domain policies were present.

---

### Applied Group Policy Objects

The system reported:

```text
Applied Group Policy Objects: N/A
```

#### Observation

* No domain-based Group Policy Objects were applied.
* This is expected for a standalone workstation that is not joined to a domain.

---

### Local Group Policy Analysis

The system reported:

```text
Local Group Policy
Filtering: Not Applied (Empty)
```

#### Observation

* No local Group Policy settings were actively configured through the Group Policy framework.

---

### Security Group Membership Review

The user account was identified as a member of several security groups, including:

```text
Everyone
Users
Administrators
Authenticated Users
Interactive
Local Account
Cloud Account Authentication
```

#### Observations

* Group memberships influence how policies and permissions are evaluated.
* Membership in the Administrators group grants elevated privileges.
* Authenticated Users and Everyone are commonly used during policy processing and access control evaluation.

---

## Security Analysis

Group Policy is one of the primary management tools used in enterprise Windows environments.

Administrators commonly use Group Policy to manage:

* Password requirements
* Account lockout settings
* Windows Defender policies
* Firewall configurations
* User restrictions
* Software deployment
* Security auditing

Although this workstation was not joined to a domain, reviewing Group Policy results demonstrated how Windows evaluates policy settings and security group memberships.

---

## Security Relevance

Group Policy is widely used by:

* System Administrators
* Security Engineers
* Active Directory Administrators
* SOC Analysts
* Incident Responders

Understanding how policies are applied is essential when investigating security events, troubleshooting configuration issues, and managing enterprise Windows environments.

---

## Key Takeaways

* Group Policy is used to manage Windows security and configuration settings.
* Standalone workstations process policies differently than domain-joined systems.
* Security group memberships influence policy evaluation.
* Enterprise environments commonly use domain-based Group Policy Objects.
* PowerShell can be used to review policy processing information.

---

## Conclusion

This lab demonstrated how Windows processes Group Policy information on a standalone workstation. Reviewing policy results, workstation configuration, and security group memberships provided insight into how Windows applies administrative controls and evaluates user permissions.

---

## Note

This lab was performed in a personal lab environment for educational and portfolio development purposes.
