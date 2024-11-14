---
date: 2024-10-31T20:31
tags:
  - "#linux"
cssclasses:
  - pen-purple
  - page-grid
---
### Permission management
***
In Linux, permissions are assigned to users and groups. Each user can be a member of different groups and membership in those groups gives the user specific, additional permissions.

The permissions can be set for the `owner`, `group` and `others` like presented in the next example

```bash
ls -l /etc/passwd
```

```bash
- rwx rw- r--   1 root root 1641 May  4 23:42 /etc/passwd
- --- --- ---   |  |    |    |   |__________|
|  |   |   |    |  |    |    |        |_ Date
|  |   |   |    |  |    |    |__________ File Size
|  |   |   |    |  |    |_______________ Group
|  |   |   |    |  |____________________ User
|  |   |   |    |_______________________ Number of hard links
|  |   |   |_ Permission of others (read)
|  |   |_____ Permissions of the group (read, write)
|  |_________ Permissions of the owner (read, write, execute)
|____________ File type (- = File, d = Directory, l = Link, ... )
```

#### Change permissions
***

Use `chmod` command to change permissions

`u` - owner
`g` - group
`o` - others
`a` - all

```bash
# add read permission for all 
chmod a+r text.txt
```

```bash
# remove write permission for the file owner 
chmod u-w text.txt
```

#### Change owner
***

```bash
chown <user>:<group> <file/directory>
chmod root:root shell && ls -l shell
```

#### SUID & SGID
***
Besides assigning direct user and group permissions, we can also configure special permissions for files by setting the `SUID` and `SGID` bits.

This allow users to run programs with the rights of another user.

It’s often the case that administrators are not familiar with the applications but still assign `SUID/SGID` bits, which leads to a high-security risk.

[For example, if administrator sets the `SUID` to `journalctl` any user with access to this application could execute a shell as `root`](https://gtfobins.github.io/gtfobins/journalctl/)

#### Sticky Bit
***
Sticky bits are a type of file permission in Linux that can be set on directories

It’s typically used on directories that are shared by multiple users to prevent one user from accidentally deleting or renaming files that are important to others

## Setting the sticky bit ensures that only the owner, the dir owner or the root user can delete or rename the files or folders in the directory 

When a sticky bit is set on a directory, it’s represented by the letter `t` in the execute permission of the dir permissions.

```bash
drw-rw-r-t 3 cry0l1t3 cry0l1t3   4096 Jan 12 12:30 scripts
drw-rw-r-T 3 cry0l1t3 cry0l1t3   4096 Jan 12 12:32 reports
```

In this example, we can see the `scripts` has `t` and `reports` has `T` sticky bit. 

`T` sticky bit means that all other users do not have `execute (x)` permission and therefore cannot see the content of the folder nor run any programs from it.

The `t` is a sticky bit where the `execute (x)` permission have been set
