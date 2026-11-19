# Level 1 -> Level 2
## Objective:
Locate and open the file called `-` in the home directory. The password stored in the file will be used to log into `bandit2`.
## Key Concepts & Commands:
- `ls`: Lists all visable files and directories in the current directory.
- `cat`: Prints all contents of a file to the terminal.
- `./`: Specifies that a file is in the current directory.
- `exit`: Terminates the current shell session.

## Investigation & Troubleshooting 
- Used `ls` to list the available files in the home directory.
- Initially tried to use `cat -` to print the contents of the `-` file but had no output.
- Realized that `-` is interpreted by `cat` as a standard input instead of a filename.
- Discovered that `./` resolves this issue by preventing `-` from being interpreted as a command option.
- Used `cat ./-` to retrieve the password for bandit2.
- Exited the current session and reconnected using the `bandit2` username and the new password to move to the next level.

## Lessons Learned
I learned that filenames that contain special characters like `-` cannot simply be referenced directly, since special characters can sometimes be interpreted as command options.
