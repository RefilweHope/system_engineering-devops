# 0x01. Shell, Permissions

## Description
This project focuses on understanding and managing file permissions in Linux, a key component of system security. It covers the basics of file ownership, user roles, and permission settings, including changing permissions for files and directories.

## Learning Objectives
By the end of this project, you should be able to explain:
- What do the commands `chmod`, `sudo`, `su`, `chown`, `chgrp` do
- Linux file permissions
- How to represent each of the three sets of permissions (owner, group, and other) as a single digit
- How to change permissions, owner and group of a file
- Why can't a normal user `chown` a file
- How to run a command with root privileges
- How to change user ID or become superuser

## Project Information
- **Weight:** 1280
- **Project Duration:** Nov 17, 2025 1:00 AM - Nov 24, 2025 1:00 AM
- **Grade Contribution:** 12.5% of overall grade
- **Auto-checker:** Runs at the end of the submission deadline

## Requirements
- All scripts must start with `#!/bin/bash`
- All files must be executable
- All scripts should be exactly 2 lines long (shebang + command)
- Scripts are tested on Ubuntu 20.04 LTS
- A README.md file at the root of the project folder is mandatory

## Repository Structure
```
system_engineering-devops/
└── 0x01-shell_permissions/
    ├── README.md
    ├── 0-iam_betty
    ├── 1-who_am_i
    ├── 2-groups
    ├── 3-new_owner
    ├── 4-empty
    ├── 5-execute
    ├── 8-James_Bond
    ├── 9-John_Doe
    ├── 11-directories_permissions
    ├── 12-directory_permissions
    └── 13-change_group
```

## Tasks

### 0. My Name Is Betty
**File:** `0-iam_betty`  
Create a script that switches the current user to the user `betty`.
- The command must be exactly 8 characters long

### 1. Who Am I
**File:** `1-who_am_i`  
Write a script that prints the effective username of the current user.

### 2. Groups
**File:** `2-groups`  
Write a script that prints all the groups the current user is part of.

### 3. New Owner
**File:** `3-new_owner`  
Write a script that changes the owner of the file `hello` to the user `betty`.

### 4. Empty!
**File:** `4-empty`  
Create a script that creates an empty file called `hello`.

### 5. Execute
**File:** `5-execute`  
Write a script that adds execute permission to the owner of the file `hello`.

### 6. James Bond
**File:** `8-James_Bond`  
Write a script that sets the permission to the file `hello` as follows:
- Owner: no permission at all
- Group: no permission at all
- Other users: all the permissions
- You are not allowed to use commas for this script

### 7. John Doe
**File:** `9-John_Doe`  
Write a script that sets the mode of the file `hello` to `-rwxr-x-wx`
- You are not allowed to use commas for this script

### 8. Directories
**File:** `11-directories_permissions`  
Create a script that adds execute permission to all subdirectories of the current directory for the owner, the group owner and all other users.
- Regular files should not be changed.

### 9. More Directories
**File:** `12-directory_permissions`  
Create a script that creates a directory called `my_dir` with permissions 751 in the working directory.

### 10. Change Group
**File:** `13-change_group`  
Write a script that changes the group owner to `school` for the file `hello`.

## Usage Examples

### Making a script executable:
```bash
chmod +x 0-iam_betty
```

### Running a script:
```bash
./0-iam_betty
```

### Checking file permissions:
```bash
ls -l
```

## Permission Notation Guide

### Symbolic Notation:
- `r` = read permission (4)
- `w` = write permission (2)
- `x` = execute permission (1)
- `-` = no permission (0)

### User Categories:
- `u` = user/owner
- `g` = group
- `o` = others
- `a` = all (u+g+o)

### Octal Notation Examples:
- `777` = `rwxrwxrwx` (all permissions for everyone)
- `755` = `rwxr-xr-x` (owner: all, group: r+x, others: r+x)
- `644` = `rw-r--r--` (owner: r+w, group: r, others: r)
- `751` = `rwxr-x--x` (owner: all, group: r+x, others: x only)
- `007` = `-------rwx` (owner: none, group: none, others: all)

## Common Commands Reference

| Command | Description |
|---------|-------------|
| `su` | Switch user |
| `sudo` | Execute command as superuser |
| `whoami` | Print effective username |
| `groups` | Print group memberships |
| `id` | Print user and group IDs |
| `chmod` | Change file permissions |
| `chown` | Change file owner |
| `chgrp` | Change group owner |
| `touch` | Create empty file |
| `mkdir` | Create directory |
| `ls -l` | List files with detailed permissions |

## Tips for Success

1. **Test your scripts locally** if you have access to a Linux environment
2. **Double-check filenames** - they must match exactly
3. **Verify the shebang** - every file must start with `#!/bin/bash`
4. **Check permissions** - ensure scripts are executable
5. **Read error messages** - the auto-checker will provide feedback
6. **Use `man` pages** - `man chmod`, `man chown`, etc. for detailed documentation

## Resources

- [Linux File Permissions Explained](https://www.linux.com/training-tutorials/understanding-linux-file-permissions/)
- [chmod Command Tutorial](https://www.computerhope.com/unix/uchmod.htm)
- [Linux Users and Groups](https://www.linux.com/training-tutorials/how-manage-users-groups-linux/)

## Author
Created as part of the System Engineering & DevOps curriculum.

## License
This project is part of an educational program and follows the institution's academic policies.
