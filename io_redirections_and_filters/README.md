# io_redirections_and_filters

Redirecting command output to files, chaining commands together with pipes, and filtering text with tools like `grep`, `tr`, `rev`, `sort`/`uniq`, `head`/`tail`, and `find`. These scripts show how small Unix utilities combine to search, transform, and reshape text streams.

## Notable files

| File | Description |
|---|---|
| `2-hellofile` / `3-twofiles` | Prints file contents with `cat`, including multiple files at once |
| `4-lastlines` / `5-firstlines` / `6-third_line` | Extracts specific lines with `head`/`tail`, including a piped combination |
| `8-cwd_state` | Redirects output to a new file with `>` |
| `9-duplicate_last_line` | Appends output to an existing file with `>>` |
| `10-no_more_js` | Finds and deletes matching files with `find ... -delete` |
| `11-directories` | Counts subdirectories with `find` piped into `wc -l` |
| `12-newest_files` | Lists the most recently modified files (`ls -t \| head`) |
| `13-unique` | Filters out duplicate lines with `sort \| uniq -u` |
| `14-findthatword` … `18-letteronly` | Various `grep` filters: plain search, `-c`, `-A`, `-v`, and anchored patterns |
| `19-AZ` / `20-hiago` | Translates or deletes characters with `tr` |
| `21-reverse` | Reverses each line of input with `rev` |

📚 See the root [CHEATSHEET.md](../CHEATSHEET.md) for the concepts used here.
