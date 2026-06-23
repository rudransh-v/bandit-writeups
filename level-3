# Bandit Level 3 → Level 4

**Goal:** Find a password hidden inside the `inhere` directory.

---

## What Tripped Me Up

Entered `inhere/`, ran `ls` — nothing. The file exists, it just doesn't show up in a plain `ls` because its name starts with `.`

Also wasted time on:
```bash
sudo cat inhere      # inhere is a directory, not a file; sudo irrelevant
cat sudo inhere      # shell read "sudo" as a filename
```

---

## Solution

```bash
find inhere
```

Output: inhere/...Hiding-From-You

`find` doesn't hide dotfiles. The output is a usable path — pass it directly to `cat`:

```bash
cat ./inhere/...Hiding-From-You
```

---

## What to Remember

Files starting with `.` are hidden from `ls` by default. Use `ls -a` or `find` to reveal them.

When `find` gives you a path, use it directly — don't ignore command output and start guessing.
