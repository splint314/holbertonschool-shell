# permissions

User identity and access-control scripts: checking who you are and which groups you belong to, switching users, and managing file permissions and ownership with `chmod`, `chown`, and `chgrp` in both numeric and symbolic mode. Together these scripts cover the full toolkit for controlling who can read, write, or execute a file on a Linux system.

## Notable files

| File | Description |
|---|---|
| `1-who_am_i` / `2-groups` | Prints the current user (`whoami`) and their groups (`groups`) |
| `0-iam_betty` | Switches to another user account with `su` |
| `5-execute` / `9-John_Doe` / `8-James_Bond` | Sets permissions with `chmod` in numeric mode |
| `6-multiple_permissions` / `7-everybody` | Sets permissions with `chmod` in symbolic mode |
| `10-mirror_permissions` | Copies permissions from another file with `chmod --reference` |
| `3-new_owner` / `13-change_group` / `14-change_owner_and_group` | Changes file owner and/or group with `chown`/`chgrp` |
| `15-symbolic_link_permissions` | Changes ownership of a symlink itself with `chown -h` |
| `12-directory_permissions` | Creates a directory with permissions preset via `mkdir -m` |

📚 See the root [CHEATSHEET.md](../CHEATSHEET.md) for the concepts used here.
