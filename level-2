# Bandit Level 2 → Level 3

**Goal:** Read a file named `spaces in this filename` in the home directory.

---

## What Tripped Me Up

The shell splits arguments on spaces. Running `cat spaces in this filename` passes four separate arguments — none of them the actual file.

Two wrong turns before the fix:
- Replaced spaces with `/` — treated it as a path, not a filename
- Tried backslashes on the wrong characters (letters instead of spaces)

---

## Solution

```bash
cat './spaces in this filename'
```

Single quotes tell the shell to treat everything inside as one literal token. The `./` prefix makes it explicit you're referencing a file in the current directory.

Alternative that also works:

```bash
cat ./spaces\ in\ this\ filename
```

Backslash before each space escapes it. More verbose and easier to get wrong — single quotes are cleaner here.

---

## What to Remember

When a filename contains spaces, you have two options: quote the whole thing, or escape each space individually. Single quotes are safer — they preserve the string exactly as written, no exceptions.
