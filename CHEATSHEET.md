# 🧠 Shell Cheat Sheet

A field guide to every shell concept exercised in this repo, grouped by directory. Each entry pairs a short, plain-English explanation with a real-world analogy.

⬅ back to [README.md](README.md)

## 📂 `basics/` — navigating and manipulating files

- **Shebang line (`#!/bin/bash`)** — the first line of every script here, telling the OS which interpreter should run the file. Like a sheet of music labeled "play on piano" — without it, the reader wouldn't know which instrument to use.
- **`pwd` / `cd`** — printing and changing the current working directory (`0-current_working_directory`, `2-bring_me_home`, `10-back` using `cd -`). Like a GPS pin that says "you are here," with a "go back to previous location" button.
- **Wildcards / globbing** — patterns like `*html`, `*~`, and `[[:upper:]]*` (seen in `14-copy_html`, `16-clean_emacs`, `15-lets_move`) that the *shell itself* expands into a list of matching filenames before the command ever runs. Like telling a librarian "pull every book whose title starts with a capital letter" instead of naming each title one by one.
- **Symbolic links (`ln -s`)** — `13-symbolic_link` creates a pointer file (`__ls__`) that references another file rather than copying it. Like a street sign pointing toward a shop: delete the sign and the shop is untouched, but delete the shop and the sign now points at nothing.
- **`file` command** — `12-file_type` inspects a file's actual content to report its type, regardless of its name or extension. Like a customs officer opening a suspicious package instead of trusting the label stuck on the outside.
- **`mkdir -p` vs `rmdir`** — `6-firstdirectory` and `17-tree` use `mkdir -p` to create (nested) directories without erroring if they already exist, while `9-firstdirdeletion` uses `rmdir`, which only removes a directory if it's already empty. Like `-p` building every missing floor of a house automatically, while `rmdir` refuses to demolish a room until it's been fully cleared out first.

## 🔐 `permissions/` — users, groups, and access rights

- **`chmod` numeric mode** — `5-execute` (`chmod 744 hello`), `7-everybody` (`chmod a+x hello`) and `9-John_Doe` (`chmod 753 hello`) set permissions as three digits (owner/group/others), each the sum of read(4) + write(2) + execute(1). Like handing out three tiers of keys to a building: a master key for yourself, a limited key for your team, and — for something like `007` in `8-James_Bond` — no key at all for the owner or group, only outsiders.
- **`chmod` symbolic mode** — `6-multiple_permissions` (`chmod ug+x,o+r hello`) adjusts specific permission bits by name instead of resetting them all at once. Like flipping individual light switches on a panel — "turn on write for the family, add read for guests" — rather than resetting the whole breaker box.
- **`chmod --reference`** — `10-mirror_permissions` copies the exact permission bits from one file (`olleh`) onto another. Like a tailor copying the precise measurements from an existing suit onto a new one instead of measuring from scratch.
- **`chown` / `chgrp`** — `3-new_owner`, `13-change_group`, and `14-change_owner_and_group` transfer ownership of a file to another user and/or group. Like transferring the title deed of a house to a new owner, or moving it into a different family trust.
- **`chown -h`** — `15-symbolic_link_permissions` changes ownership of a symbolic link itself (`_hello`) rather than the file it points to. Like signing the deed for the mailbox, not the house it's mounted in front of.
- **`mkdir -m`** — `12-directory_permissions` creates a directory with its permissions set at creation time (`mkdir -m 751 my_dir`). Like a house built with the alarm code pre-programmed, instead of setting it after moving in.
- **`su` — switch user** — `0-iam_betty` runs `su betty` to temporarily become another user account. Like borrowing a coworker's badge to access their office for a few minutes, rather than living there permanently.
- **`whoami` / `groups`** — `1-who_am_i` and `2-groups` print the current user's identity and the groups they belong to. Like an ID badge that shows both your name and which departments you're cleared to enter.

## 🧮 `init_files_variables_and_expansions/` — environment, variables, and expansions

- **Aliases** — `0-alias` defines `alias ls="rm -f *"`, a deliberately dangerous example of shadowing a trusted command with a destructive one. Like relabeling the "eject" button on a machine as "play" — anyone who presses what they believe is `ls` actually wipes the directory.
- **Environment variables (`$USER`, `$PATH`)** — `1-hello_you` reads `$USER`, and `2-path` extends `$PATH` with `export PATH="$PATH:/action"`. Like a librarian checking an ever-growing list of shelves, in order, whenever asked to find something by name alone.
- **Global vs. local variables (`export`)** — `6-create_local_variable` sets `BEST=School` (visible only in the current shell), while `7-create_global_variable` uses `export BEST=School` (visible to every subprocess spawned afterward). Like a sticky note on your own desk (local — gone once you leave the room) versus a memo pinned to the public bulletin board (exported — every employee downstream can read it).
- **`printenv` vs. `set`** — `4-global_variables` lists only exported/environment variables, while `5-local_variables` lists every shell variable, including local ones. Like the company's official HR directory (`printenv`, registered staff only) versus the full sign-in sheet at the front desk (`set`, every visitor included).
- **Counting `$PATH` entries** — `3-paths` pipes `$PATH` through `tr ':' '\n' | grep -c .` to turn colon-separated entries into lines and count them. Like slicing a run-on sentence into individual words by replacing every comma with a line break, then counting the lines.
- **Arithmetic expansion `$(( ))`** — `8-true_knowledge` (`128 + TRUEKNOWLEDGE`), `9-divide_and_rule` (division), and `10-love_exponent_breath` (`**` exponent) do math directly inside the shell. Like doing arithmetic right on the back of a receipt instead of reaching for a separate calculator.
- **Base conversion (`2#`, `printf %x`)** — `11-binary_to_decimal` reads a binary string with `$((2#$BINARY))`, and `14-decimal_to_hexadecimal` formats a number as hex with `printf "%x\n"`. Like a translator converting a temperature between Celsius and Fahrenheit — same value, different notation.
- **Brace expansion `{a..z}`** — `12-combinations` expands `{a..z}{a..z}` into every two-letter pair before piping through `tr` and `grep -v oo` to drop the ones containing "oo". Like an order form with a range field ("flavors A through Z") that auto-expands into one ticket per flavor before the kitchen ever sees it.
- **`printf` formatting** — `13-print_float` (`%.2f`) and `14-decimal_to_hexadecimal` (`%x`) format raw values into a fixed output shape. Like a receipt printer that always rounds a price to two decimals, no matter what raw number the register sends it.

## 🔀 `io_redirections_and_filters/` — redirections, pipes, and filters

- **Output redirection `>` vs. `>>`** — `8-cwd_state` (`ls -la > ls_cwd_content`) overwrites/creates a file from scratch, while `9-duplicate_last_line` (`tail -n 1 iacta >> iacta`) appends to the end without erasing what's already there. Like starting a fresh receipt (`>`) versus adding one more line to a running tab (`>>`).
- **Pipes `|`** — `6-third_line` (`head -n 3 iacta | tail -n 1`), `12-newest_files` (`ls -t | head -10`), and `13-unique` (`sort | uniq -u`) chain commands so one's output becomes the next's input. Like a factory assembly line where the output conveyor of one machine feeds directly into the input hopper of the next — no one has to carry parts between them by hand.
- **`head` / `tail -n`** — `4-lastlines` and `5-firstlines` grab only the first or last 10 lines of a file. Like a magazine editor pulling just the opening or closing paragraph of a long article for a preview.
- **`find ... -delete`** — `10-no_more_js` runs `find . -type f -name "*.js" -delete` to remove only matching files. Like a robot vacuum that identifies and removes only the items matching a specific description, leaving everything else in the room untouched.
- **`find -type d` + `wc -l`** — `11-directories` counts subdirectories by piping `find`'s output into `wc -l`. Like a scout reporting "found a room" every time one is spotted, then someone tallying up the reports at the end.
- **`grep` filtering** — `14-findthatword` (`grep "root"`) searches for a keyword; `15-countthatword` (`grep -c`) counts matches instead of printing them; `16-whatsnext` (`grep -A 3`) shows the 3 lines of context *after* a match; `17-hidethisword` (`grep -v`) prints every line that does *not* match; `18-letteronly` (`grep "^[A-Za-z]"`) anchors the match to the start of the line. Like a detective scanning a transcript: search for a name, count its mentions, read a few lines past it for context, exclude every page that mentions it, or flag only sentences that *open* with a specific type of word.
- **`tr` — character translation** — `19-AZ` and `20-hiago` (`tr -d`) replace or delete specific characters wherever they appear. Like a proofreader doing a global find-and-replace of one letter for another across an entire manuscript.
- **`rev`** — `21-reverse` prints each input line backwards. Like reading a line of text reflected in a mirror.
- **Sorting out duplicates (`sort | uniq -u`)** — `13-unique` sorts input so identical lines sit next to each other, then keeps only the ones with *no* neighbor match. Like sorting a stack of raffle tickets by number and pulling aside only the ones that never found a matching pair.
- **Quoting special characters** — `7-file` writes to a filename packed with shell metacharacters (`*`, `\`, `$`, `?`, quotes) by carefully escaping and quoting each one. Like typing an oddly-punctuated password on a phone that keeps trying to autocorrect it — every special character has to be shielded individually so it's taken literally.

---

⬅ back to [README.md](README.md)
