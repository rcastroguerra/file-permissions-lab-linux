# File Permissions in Linux

## Project Description

As a security professional in a large organization, I used Linux commands to review and manage file permissions. This ensures that only authorized users can access or modify critical resources. Through this activity, I reinforced security policies, protected sensitive files, and restricted unnecessary access.

---

## Check File and Directory Details

**Command used:**

```bash
ls -la /home/research/projects
```

**Example of observed permission:**

```readline
-rw-rw-rw-
```

This command lists all files and subdirectories, including hidden files. It displays permissions, owner, group, size, and modification date.

---

## Describe the Permissions String

**Permission string:**

```readline
-rw-rw-rw-
```

**Explanation:**

- `-`: regular file  
- `rw-`: owner can read and write  
- `rw-`: group can read and write  
- `rw-`: others can also read and write  

This level of access is risky. Permissions should be adjusted to comply with the organization's security policies.

---

## Change File Permissions

**Command applied:**

```bash
chmod o-w summary.txt
```

**New status:**

```readline
-rw-rw-r--
```

This change removes write access for other users.

---

## Change File Permissions on a Hidden File

**File:** `.project_x.txt`

**Command applied:**

```bash
chmod 440 .project_x.txt
```

**New status:**

```readline
-r--r----- 1 researcher2 research 1346 Jun 14 09:00 .project_x.txt
```

Read-only permissions for owner and group, with no access for other users.

---

## Change Directory Permissions

**Directory:** `drafts` (owned by `researcher2`)

**Commands applied:**

```bash
chown researcher2 drafts
chmod 700 drafts
```

**Result:**

```readline
drwx------  researcher2  research  4096 Jun 14 09:15 drafts
```

Only the owner has full access; all other users are excluded.

---

## Octal Permission Values Explained

Each digit in `chmod` represents a combination of permissions in binary format:

| Digit | Binary | Permissions | Description                 |
|--------|--------|-------------|-----------------------------|
| 0      | 000    | ---         | No permissions              |
| 1      | 001    | --x         | Execute only                |
| 2      | 010    | -w-         | Write only                  |
| 3      | 011    | -wx         | Write and execute           |
| 4      | 100    | r--         | Read only                   |
| 5      | 101    | r-x         | Read and execute            |
| 6      | 110    | rw-         | Read and write              |
| 7      | 111    | rwx         | All permissions             |

**Usage example:**

```bash
chmod 750 script.sh
```

Grants:
- 7 (`rwx`) to the owner  
- 5 (`r-x`) to the group  
- 0 (`---`) to others

---

## Summary

During this activity, I reviewed and adjusted permissions on key files and directories using commands like `ls -la`, `chmod`, and `chown`. I corrected insecure configurations, protected sensitive files such as `.project_x.txt`, and restricted access to the `drafts` directory. This practice demonstrates my competence in using Linux to strengthen security in Unix-based systems.
