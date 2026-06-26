# Bandit Level 5 → 6

## Objective
Find the file under the `inhere` directory that is human-readable, exactly 1033 bytes, and not executable. Read the password stored in it.

## Solution

```bash
find inhere -type f -size 1033c ! -perm /111
cat inhere/maybehere07/.file2
```

## Walkthrough

The `inhere` directory contains multiple subdirectories, each with several files — manually checking every one isn't practical. The level gives three conditions, and `find` has a flag for each.

- `-type f` restricts results to regular files, excluding directories and symlinks.
- `-size 1033c` matches files of exactly 1033 bytes (`c` = bytes).
- `! -perm /111` excludes any file with an execute bit set. `/111` covers owner, group, and others execute bits — the `!` negates the match.

Combining all three returns a single result: `inhere/maybehere07/.file2`. Reading it gives the password.

## Key concepts

- **`find` with multiple filters** — conditions are ANDed by default; all must match
- **`-size` suffix** — `c` = bytes, `k` = KiB, `M` = MiB
- **`-perm /111`** — matches if any of the three execute bits are set; `!` inverts it
- **`-type f`** — regular files only; excludes directories (`d`) and symlinks (`l`)
