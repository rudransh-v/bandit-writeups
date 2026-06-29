# Bandit Level 6 → 7

## Objective
Find a file stored somewhere on the server owned by user `bandit7`, group `bandit6`, and exactly 33 bytes in size.

## Solution

Search the entire filesystem using `find` with three filters combined:

```bash
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

This returns a single path. Read it with `cat`.

## Breakdown

| Flag | Meaning |
|---|---|
| `/` | Search from filesystem root |
| `-user bandit7` | Owned by this user |
| `-group bandit6` | Owned by this group |
| `-size 33c` | Exactly 33 bytes (`c` = bytes) |
| `2>/dev/null` | Discard permission errors from directories you can't access |

## Key concept

Linux has two separate output streams: `stdout` (normal output) and `stderr` (errors). When searching `/` without root privileges, `find` throws hundreds of `Permission denied` errors on stderr — but the valid result still prints to stdout. `2>/dev/null` silences stderr
