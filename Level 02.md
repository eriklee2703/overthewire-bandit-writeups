# Level 1 -> Level 2
## Objective:
Locate and open the file called `-` in the home directory. The password stored within the file will be used to log into `bandit2`.
## Key Concepts & Commands:
- `ls`: Lists all the files in the current directory.
- `cat`: Displays the contents of a file directly to the terminal (standard output).
- `./`: Refers to the current directory, allowing you to explicitly reference a file in the present folder.
- `exit`: Terminates the current shell session, disconnecting from the remote server.

## Investigation & Troubleshooting 
- Used `ls` to list the available files in the home directory, which revealed a single file named `-`.
- Initially attempted  `cat -` to print the contents of the `-` file but had no output.
- Realized `-` is interpreted by `cat` as a standard input instead a filename.
- Discovered `./` fixes this issue forcing the command to interpret `./` as a relative file path instead of a special argument.
- Used `cat ./-` to display the file contents and retrieve the password for bandit2.
- Exited the current session and reconnect using the `bandit2` username and the new 32 bit password to move to the next level.

## Lessons Learned
I learned that filenames containing special characters such as `-` can sometimes be interpreted as a command option instead. Using `./` 
explicitly specifies that the target is a file in the current directory.
