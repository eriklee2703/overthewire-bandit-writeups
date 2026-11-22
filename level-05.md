# Level 4 -> Level 5
## Objective:
Locate the password in the only human-readable file within the inhere directory. The password stored in the file will be used to log into `bandit5`.
## Key Concepts & Commands:
- `file`: Identifies the file type.
- `*`: A wildcard representing zero or more characters.

## Investigation & Troubleshooting 
- Navigated to the `inhere` directory with `cd inhere`.
- Discovered 10 files listed in the `inhere` directory.
- Found using the `file` command which identifies the file type.
- While manually searching is feasible, wanted to use a single line to search for the only human-readable file.
- Discovered the `*` can help accomplish this by pattern matching 0 or more characters with `./*`.
- To be more specific in this level, since every filename begins with `-file0`, I added a `*` to search for only files starting with that prefix.
```bash
bandit4@bandit:~/inhere$ file -- -file0*
-file00: data
-file01: data
-file02: Non-ISO extended-ASCII text, with NEL line terminators, with escape sequences
-file03: data
-file04: data
-file05: data
-file06: data
-file07: ASCII text
-file08: data
-file09: Non-ISO extended-ASCII text, with no line terminators
```
- Identified `-file07` was the only human-readable file.
- Used `cat ./-file07` to retrieve the password for `bandit5`.
- After retrieving the password, exited out of the current session and reconnected using the `bandit5` username and the new password to move on to the next level.

## Lessons Learned
I learned how to optimally search using the `*`, which can be much more effective especially if varying filenames exist.
