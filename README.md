# Shell 🐚

> First steps in the Linux shell — navigation, file manipulation, and permissions, one script at a time.

> 🎓 Part of the Software Engineering curriculum at **Holberton School Toulouse**.

![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

## 📖 About

This repository holds a set of one-line Bash scripts, each solving a single, tightly scoped shell task — the kind of muscle-memory commands every Linux user ends up typing daily. It's split into two themes: everyday filesystem navigation and manipulation (`basics/`), and user identity and permission management (`permissions/`). Every script starts with a `#!/bin/bash` shebang and is meant to be run directly from the command line.

## 📂 Project Structure

| Path | Description |
|---|---|
| `basics/` | Navigation and file operations: `pwd`, `ls` variants, `cd`, `mkdir -p`, `mv`, `rm`/`rmdir`, symbolic links (`ln -s`), wildcard copies/moves |
| `permissions/` | User and permission scripts: `su`, `whoami`, `groups`, and `chmod` in numeric mode |

## 🧠 Cheat Sheet

- **Shebang line (`#!/bin/bash`)** — the first line of every script here, telling the OS which interpreter should run the file. Like a sheet of music labeled "play on piano" — without it, the reader wouldn't know which instrument to use.
- **`pwd` / `cd`** — printing and changing the current working directory (`0-current_working_directory`, `2-bring_me_home`, `10-back` using `cd -`). Like a GPS pin that says "you are here," with a "go back to previous location" button.
- **Wildcards / globbing** — patterns like `*html`, `*~`, and `[[:upper:]]*` (seen in `14-copy_html`, `16-clean_emacs`, `15-lets_move`) that the *shell itself* expands into a list of matching filenames before the command ever runs. Like telling a librarian "pull every book whose title starts with a capital letter" instead of naming each title one by one.
- **Symbolic links (`ln -s`)** — `13-symbolic_link` creates a pointer file (`__ls__`) that references another file rather than copying it. Like a street sign pointing toward a shop: delete the sign and the shop is untouched, but delete the shop and the sign now points at nothing.
- **`chmod` numeric mode** — `5-execute` (`chmod 755 hello`) and `7-everybody` (`chmod 640 hello`) set permissions as three digits (owner/group/others), each the sum of read(4) + write(2) + execute(1). Like handing out three tiers of keys to a building: a master key for yourself, a limited key for your team, and for `640`, no key at all for outsiders — not even a peek inside.
- **`su` — switch user** — `0-iam_betty` runs `su betty` to temporarily become another user account. Like borrowing a coworker's badge to access their office for a few minutes, rather than living there permanently.
- **`whoami` / `groups`** — `1-who_am_i` and `2-groups` print the current user's identity and the groups they belong to. Like an ID badge that shows both your name and which departments you're cleared to enter.
- **`mkdir -p` vs `rmdir`** — `6-firstdirectory` and `17-tree` use `mkdir -p` to create (nested) directories without erroring if they already exist, while `9-firstdirdeletion` uses `rmdir`, which only removes a directory if it's already empty. Like `-p` building every missing floor of a house automatically, while `rmdir` refuses to demolish a room until it's been fully cleared out first.

## 📬 Contact

- 💬 Discord: kevin_rigal
- 📧 Email: kevinrigal.contact@gmail.com
- 🐙 GitHub: [@sharingankid](https://github.com/sharingankid)
