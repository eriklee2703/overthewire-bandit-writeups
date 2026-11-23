# Level 9 -> Level 10
## Objective:
The password is stored within a file named `data.txt` that contains one of the few human-readable strings, preceded by several ‘=’ characters. Create a search command to identify the password and use it move to the next level.
## Key Concepts & Commands:
- `strings`: Lists all visable files and directories in the current directory.
- `cat`: Prints the sequences of prinatable characters in a file. By default, the minimum is four characters.
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
