# Bandit Level 4 → 5

## Objective
Find the only human-readable file inside the `inhere` directory and read the password stored in it.

## Solution

```bash
cd inhere
file ./*
cat ./-file07
```

## Walkthrough

The `inhere` directory contains 10 files named `-file00` through `-file09`. Since only one is human-readable, the goal is to identify file types before reading.

Running `file ./*` lets the shell expand `*` into all filenames in the current directory and passes them to `file` in one shot. The output shows 9 files as data (binary) and one — `-file07` — as ASCII text.

Reading `-file07` with `cat ./-file07` gives the password. The `./` prefix is necessary because the filename starts with `-`; without it, the shell interprets it as a flag.

## Key concepts

- **`file` command** — reads file content (not extension) to determine type
- **Wildcards / globbing** — `*` is expanded by the shell before the command runs; the command never sees the `*`
- **`./` prefix** — required for filenames starting with `-` to avoid flag misinterpretation
