# 01 — Local Users and Groups

## Goal

Understand how Windows manages local user accounts and group memberships.

User and group management is a foundational administrative task and plays an important role in authentication, authorization, and access control.

---

## What I Did

* Reviewed local user accounts.
* Examined local group memberships.
* Identified administrative and standard user accounts.
* Documented account information.
* Reviewed access control concepts.

---

## Tools Used

### Windows Computer Management

Used to review local users and groups.

### Local Users and Groups

Used to review user account and group information.

---

## What I Observed

Windows uses local user accounts and security groups to manage authentication and authorization on the workstation.

The system contained both user-created and built-in accounts. Several built-in security groups were also present to support administration, logging, remote management, and operating system functionality.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-01-local-users-and-groups/
```

Files:

```text
local_users_review.png
local_groups_review.png
```

---

## Investigation Findings

### Local User Account Review

The following local user accounts were identified:

```text
Administrator
angel
DefaultAccount
Guest
WDAGUtilityAccount
WsiAccount
```

Observations:

* The primary active account was `angel`.
* The built-in `Administrator` account was disabled.
* The built-in `Guest` account was disabled.
* Several system-managed accounts existed to support Windows functionality and security features.

### Local Group Review

The following groups were identified:

```text
Administrators
Device Owners
Distributed COM Users
Event Log Readers
Guests
Hyper-V Administrators
IIS_IUSRS
OpenSSH Users
Performance Log Users
Performance Monitor Users
Remote Management Users
System Managed Accounts Group
User Mode Hardware Operators
Users
```

Observations:

* The `Administrators` group provides unrestricted access to the system.
* The `Event Log Readers` group allows members to review Windows event logs.
* The `OpenSSH Users` group controls SSH access to the workstation.
* The `Remote Management Users` group supports remote administration capabilities.

### Security Analysis

Windows uses security groups to simplify access control and privilege assignment.

Rather than assigning permissions individually to every user, permissions can be granted through group membership. This approach improves administrative efficiency and supports the principle of least privilege.

The workstation appeared to follow standard Windows security practices, including disabling the built-in Administrator and Guest accounts.

### Conclusion

Local users and groups provide the foundation for identity and access management within Windows environments. Reviewing user accounts and security groups demonstrated how Windows organizes permissions and controls access to system resources.
