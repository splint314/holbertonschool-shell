# Shell 🐚

> First steps in the Linux shell — navigation, file manipulation, and permissions, one script at a time.

> 🎓 Part of the Software Engineering curriculum at **Holberton School Toulouse**.

![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat&logo=gnubash&logoColor=white)
![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat&logo=linux&logoColor=black)

## 📖 About

This repository holds a set of small, tightly scoped Bash scripts, each solving a single shell task — the kind of muscle-memory commands every Linux user ends up typing daily. It's organized into four themes: everyday filesystem navigation and manipulation (`basics/`), user identity and permission management (`permissions/`), shell initialization, variables, and expansions (`init_files_variables_and_expansions/`), and I/O redirections and text filters (`io_redirections_and_filters/`). Every script starts with a `#!/bin/bash` shebang and is meant to be run directly from the command line.

## 📂 Project Structure

| Path | Description |
|---|---|
| `basics/` | Navigation and file operations: `pwd`, `ls` variants, `cd`, `mkdir -p`, `mv`, `rm`/`rmdir`, symbolic links (`ln -s`), wildcard copies/moves |
| `permissions/` | User and permission scripts: `su`, `whoami`, `groups`, and `chmod`/`chown`/`chgrp` in numeric and symbolic mode |
| `init_files_variables_and_expansions/` | Shell startup, environment vs. local variables, `export`, `PATH`, aliases, arithmetic and brace expansion, `printf` formatting |
| `io_redirections_and_filters/` | Redirections (`>`, `>>`), pipes, and text filters: `head`/`tail`, `grep`, `tr`, `rev`, `sort`/`uniq`, `find` |

## 🧠 Cheat Sheet

All the key concepts from this repo, explained with analogies → **[CHEATSHEET.md](CHEATSHEET.md)**

## 📬 Contact

- 💬 Discord: kevin_rigal
- 📧 Email: kevinrigal.contact@gmail.com
- 🐙 GitHub: [@sharingankid](https://github.com/sharingankid)
