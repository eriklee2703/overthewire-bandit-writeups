# Level 2 -> Level 3
## Objective:
Open a file in the home directory named `-- spaces in this filename--`. The password stored in the file will be used to log into `bandit3`.
## Key Concepts & Commands:
- `ls`: Lists all visable files and directories in the current directory.
- `cat`: Prints all contents of a file to the terminal.
- `./`: Specifies that a file is in the current directory.
- `--`: Prevents an argument to be treated as an option.

## Investigation & Troubleshooting 
- Used `ls` to see all the available files in the home directory.
- This level is similar to the last level so attempted the same method `cat ./--spaces in a filename` but got a standard error message.
- What's different about this level is that the filename has spaces in it, causing the shell to treat the file as multiple arguments instead.
- To resolve this issue, used quotes around the filename so that it would be interpreted as a single filename along with `./` to specify the current filename.
- Also found `cat -- "--spaces in a filename--"` works too as it tells the `cat` command that a `-` and anything preceding is to be treated as a filename and not an option.
- After retrieving the password, exited out of the current session and reconnected using the `bandit3` username and the new password to move on to the next level.

## Lessons Learned
I learned that filenames that contain spaces in it require quotations and that there are multiple ways to reference a file.
