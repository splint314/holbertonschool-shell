# init_files_variables_and_expansions

Shell environment fundamentals: the difference between local and exported (global) variables, reading and extending `$PATH`, defining aliases, and using the shell's built-in arithmetic, base-conversion, and brace expansion. Several scripts also use `printf` to format numeric output precisely.

## Notable files

| File | Description |
|---|---|
| `0-alias` | Defines a (deliberately dangerous) alias with `alias` |
| `1-hello_you` | Reads the `$USER` environment variable |
| `2-path` / `3-paths` | Extends and inspects `$PATH` |
| `4-global_variables` / `5-local_variables` | Lists environment vars (`printenv`) vs. all shell vars (`set`) |
| `6-create_local_variable` / `7-create_global_variable` | Contrasts a plain assignment with an `export`ed one |
| `8-true_knowledge` / `9-divide_and_rule` / `10-love_exponent_breath` | Arithmetic expansion `$(( ))` |
| `11-binary_to_decimal` / `14-decimal_to_hexadecimal` | Base conversion using `2#` and `printf %x` |
| `12-combinations` | Brace expansion (`{a..z}`) combined with `tr` and `grep -v` |
| `13-print_float` | Formats a number with `printf "%.2f"` |

📚 See the root [CHEATSHEET.md](../CHEATSHEET.md) for the concepts used here.
