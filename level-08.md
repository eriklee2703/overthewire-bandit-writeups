# Level 7 -> Level 8
## Objective:
The password is stored next to the word "millionth" in a file named `data.txt`, located within the home directory. This password will be used to move on to `bandit8`.
## Key Concepts & Commands:
- `grep`: Searches for patterns within a file and displays matching lines.

## Investigation & Troubleshooting 
- Displaying the contents of `data.txt` using the `cat` command listed hundreds of thousands of words, making manually searching nearly impossible.
- One command that resolves this issue is the `grep`, which enables search for specific words or patterns within a file.
- Specified the word "millionth" as the search term in `data.txt`. This printed the entire line containing the matching word, along with the password.
```bash
bandit7@bandit:~$ grep "millionth" data.txt
millionth ***********
```
- After retrieving the password, exited out of the current session and reconnected using the `bandit8` username and the new password to move on to the next level.

## Lessons Learned
I learned how to use `grep` to search through a file for specific words or patterns. Unlike the `find` command which is used to search for files or directories based on a specified criteria, `grep` searches at a more granular level inside of a file. This is especially useful in situations when manually searching in a file would be impractical.
