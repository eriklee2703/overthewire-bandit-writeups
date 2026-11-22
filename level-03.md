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
- Initially, tried to use `cat -` similarly to the last level but `-` file resulted without an output.
- Realized that the `-` file was interpreted by `cat` as a standard input instead of a filename.
- `./` resolves this issue by preventing `-` from being interpreted as a command option.
- Used `cat ./-` to display contents in the `-` file and retrieve the password for bandit2.
- After retrieving the password, exited out of the current session and reconnected using the `bandit2` username and the new password to move on to the next level.

## Lessons Learned
I learned that filenames that contain special characters like `-` cannot simply be referenced directly, since special characters can sometimes be interpreted as command options.
