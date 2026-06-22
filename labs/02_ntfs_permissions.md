# Lab 02 — File and Folder Permissions

## Goal

Understand how Windows uses permissions and access control lists (ACLs) to regulate access to files and folders.

File and folder permissions are a core component of authorization within Windows environments. They determine which users and groups can read, modify, delete, or manage resources on a system.

---

## What I Did

* Created a test folder for permission analysis.
* Reviewed folder security settings through Windows Properties.
* Examined users and groups with access to the folder.
* Investigated advanced security settings.
* Identified inherited permissions and ownership information.
* Analyzed how Allow and Deny permissions affect access control.

---

## Tools Used

### Windows File Explorer

Used to access folder properties and review security settings.

### Advanced Security Settings

Used to review ownership, inheritance, and detailed permission entries.

---

## What I Observed

Windows controls access to files and folders through Access Control Lists (ACLs).

Permissions can be assigned to users and groups, while inheritance allows child folders to automatically receive permissions from parent directories. Ownership also determines who can modify permission settings.

---

## Evidence Collected

### Screenshots

Store screenshots in:

```text
screenshots/lab-02-file-and-folder-permissions/
```

Files:

```text
folder_permissions_review.png
advanced_permissions_review.png
```

---

## Investigation Findings

### Folder Security Review

The following security principals were assigned permissions to the folder:

```text
Everyone
SYSTEM
Ang B
Administrators
```

The Security tab showed multiple permission entries used to control access to the folder and its contents.

---

### Advanced Security Review

The folder owner was identified as:

```text
Ang B (angelica2005bravo@gmail.com)
```

Ownership allows the user to manage permission settings and control access to the resource.

---

### Permission Inheritance

The folder inherited permissions from:

```text
C:\Users\angel\
```

This indicates the folder was using inherited permissions from the parent directory rather than unique permissions configured specifically for the folder.

Permission inheritance simplifies administration and ensures consistent security settings across folders and files.

---

### Access Control Entries

The following permission entries were identified:

```text
SYSTEM
Administrators
Ang B
Everyone
```

Observed access levels included:

```text
SYSTEM          → Full Control
Administrators  → Full Control
Ang B           → Full Control
```

---

### Deny Permission Analysis

An explicit permission entry was observed:

```text
Everyone → Deny → Delete Subfolders and Files
```

This is significant because Deny permissions take precedence over Allow permissions when Windows evaluates access requests.

The presence of an explicit Deny entry demonstrates how administrators can prevent specific actions even when users may otherwise have broad permissions.

---

### Security Analysis

Windows authorization relies on Access Control Lists (ACLs) to determine what actions users and groups can perform on resources.

Key concepts observed during this lab included:

* Ownership
* Access Control Entries (ACEs)
* Permission inheritance
* Full Control permissions
* Explicit Deny permissions

These mechanisms help organizations enforce the principle of least privilege and protect sensitive resources from unauthorized modification.

---

## Security Relevance

Understanding file and folder permissions is essential for:

* Security Operations Center (SOC) investigations
* System administration
* Access control reviews
* Insider threat investigations
* Active Directory administration
* Incident response

Analysts frequently review permissions to determine whether unauthorized access, privilege escalation, or improper configuration contributed to a security event.

---

## Key Takeaways

* Windows uses ACLs to control access to files and folders.
* Permissions can be assigned to users and groups.
* Folder ownership determines who can manage permissions.
* Permission inheritance simplifies administration.
* Explicit Deny permissions override Allow permissions.
* Access control is a foundational cybersecurity concept.

---

## Conclusion

This lab demonstrated how Windows implements authorization through file and folder permissions. Reviewing ACLs, inheritance, ownership, and permission entries provided practical experience with access control concepts that are commonly encountered in enterprise Windows environments.

---

## Note

This lab was performed in a personal lab environment for educational and portfolio development purposes.
