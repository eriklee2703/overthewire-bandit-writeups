# Level 5 -> Level 6
## Objective:
The password is stored in a file somewhere amongst in the `inhere` directory containing the following properties: human-readable, 1033 bytes in size, and not executable.

## Key Concepts & Commands:
- `find`: Searches through directory trees to locate a directory or file based off specified criteria.
- `find -type f`: one of many `find` options that filters for regular files.
- `find -size`: filters based on much disk space is used.
- `find -executable`: filters for only executable files.
- `!`: a logical NOT operator that inverts an argument.

## Investigation & Troubleshooting 
- Navigated to the `inhere` directory with `cd inhere`.
- Within the directory contains thousands of possible directories and files, so searching manually wouldn't be appropriate.
- Used the find command to help filter my search to meet all the criteria stated above.
- Going through the `man` page and assist online, was able to find the arguments needed to query for the right file.

```bash
bandit5@bandit:~/inhere$ find -type f -size 1033c ! -executable
./maybehere07/.file2
```
- `-size 1033c` searches for files that are exactly 1033 bytes.
- The `!` operator reverses the `-executable` option to any non-executable file.
- Located the correct file that met all the criteria was stored in a directory named `maybehere07` named `.file2`.
- After retrieving the password using the `cat` command, exited out of the current session and reconnected using the `bandit6` username and the new password to move on to the next level.

## Lessons Learned
I realized how powerful of a tool linux can be and how efficiently it can be used to search through large amounts of data by combining different options. This level helped me become more comfortable troubleshooting for specific command options using the `man` page.
