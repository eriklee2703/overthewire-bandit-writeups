# Level 0 -> Level 1
## Objective:
Locate and open the file called `readme` in the home directory. The password stored within the file will be used to log into `bandit1`.
## Key Concepts & Commands:
- `ls`: Lists all the files in the current directory.
- `cat`: Displays the contents of a file directly to the terminal (standard output).
- `exit`: Terminates the current shell session, disconnecting from the remote server.

## Investigation & Troubleshooting 
- Used `ls` to list the available files in the home directory.
- Used `cat` to print the contents of the `readme` file.
- After retrieving the password, initially attempted to start another SSH session within the existing session.
- Realized I needed to exit the current session and reconnect using the `bandit1` username to move to the next level.

## Lessons Learned
I learned that each SSH connection authenticates a single user session. In order to switch from `bandit0` -> `bandit1` while maintaining a single session, I needed to establish a
new SSH connection with the new credentials. Exiting out of the existing session was one way to accomplish this.
