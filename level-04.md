# Level 3 -> Level 4
## Objective:
Locate a hidden file within the `inhere` directory. The password stored in the file will be used to log into `bandit4`.
## Key Concepts & Commands:
- `cd`: Change directories.
- `ls -a`: Lists all files and directories, visible and hidden in the current directory.
- `ls -la`: Lists all files and directories, including hidden in the current directory (long 

## Investigation & Troubleshooting 
- Used `ls` to locate the `inhere` directory.
- To navigate into the `inhere` directory, used `cd inhere`.
- When trying to list the files in the `inhere` directory, nothing appeared since the file is hidden.
- A c
- Used `cat ./-` to display contents in the `-` file and retrieve the password for bandit2.
- After retrieving the password, exited out of the current session and reconnected using the `bandit2` username and the new password to move on to the next level.

## Lessons Learned
I learned that filenames that contain special characters like `-` cannot simply be referenced directly, since special characters can sometimes be interpreted as command options.
