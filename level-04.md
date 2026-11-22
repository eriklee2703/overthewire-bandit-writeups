# Level 3 -> Level 4
## Objective:
Locate a hidden file within the `inhere` directory. The password stored in the file will be used to log into `bandit4`.
## Key Concepts & Commands:
- `cd`: Change directories.
- `man`: A manual page for a command.
- `whatis`: Provides a one-line description of a command.
- `ls -a`: Lists all files and directories, visible and hidden, in the current directory.
- `ls -la`: Lists all files and directories, including hidden in the current directory (long listing format).

## Investigation & Troubleshooting 
- Used `ls` to locate the `inhere` directory.
- To navigate into the `inhere` directory, used `cd inhere`.
- When trying to list the files in the `inhere` directory, nothing appeared since the file is hidden.
- Using `ls` without any options only lists the visible files and directories. Looking through `man ls`, found that both `ls -a` and `ls -la` list hidden files and directories.

```bash
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls -a
.  ..  ...Hiding-From-You
bandit3@bandit:~/inhere$ ls -la
total 12
drwxr-xr-x 2 root    root    4096 Oct 25 13:37 .
drwxr-xr-x 3 root    root    4096 Oct 25 13:37 ..
-rw-r----- 1 bandit4 bandit3   33 Oct 25 13:37 ...Hiding-From-You
```
- Noticed files are hidden if a `.` is placed at the start of a filename.
- Used `cat ...Hiding-From-You` to retrieve the password.
- After retrieving the password, exited out of the current session and reconnected using the `bandit4` username and the new password to move on to the next level.

## Lessons Learned
I learned that file can be hidden when `.` is placed in front of a filename. Also the discovery of the `man` page along with `whatis` should help me better understand how to use each command.
