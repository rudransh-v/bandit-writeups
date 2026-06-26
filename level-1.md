# Bandit Level 1 — Dashed Filename

> The password file is named `-`. Most Linux commands treat `-` as stdin,
> not a filename. This level teaches you how to handle that.

---

## Goal
Read the contents of a file named `-` in the home directory and get
the password for Level 2.

---

## Commands Used

| Command | Purpose |
|--------|---------|
| `pwd` | Confirm current directory |
| `find -` | Locate the file named `-` |
| `du -` | Verify file has content |
| `cat ./-` | Read the file using explicit relative path |

---

## The Fix

```bash
cat ./-
```

Prefixing with `./` turns `-` from a bare argument into an explicit path,
removing its special meaning.

---

## Why Other Attempts Failed

| Command | What Happened | Why |
|--------|---------------|-----|
| `cat -` | Waited for keyboard input | `-` = stdin by convention |
| `cd -` | Switched to previous directory | Bash built-in, not a filename |
| `file -` | Read from stdin | Same convention as above |
| `cat /-` | No such file or directory | `/-` looks for `-` inside root `/` |
| `cat ./ -` | Directory error | Space splits it into two arguments |

---

## Key Takeaway
Whenever a filename is `-`, use `./-` to reference it explicitly.
Check `man <command>` and search for `-` to see if it has special behavior.
