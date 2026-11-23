# Level 9 -> Level 10
## Objective:
The password is stored in a file named `data.txt` and is one of the few human-readable strings within the file. The password is preceded by several "=" characters. Create the appropriate search command to identify the password and use it to proceed to the next level.

## Key Concepts & Commands:
- `strings`: Extracts the sequences of printable characters in a file. By default, displays sequences of at least four characters.
- `grep`: Searches for specific text patterns within a file or command output.

## Investigation & Troubleshooting 
- In the `data.txt` file contains mostly non-binary data, making it too difficult to identify the password by simply displaying the contents.
- Needed a way to extract all the human printable lines in the file, which was achieved with the `strings` command.
- After extracting all the human readable lines, piped this into a `grep` search for lines that contained multiple "=" characters.

```bash
bandit9@bandit:~$ strings data.txt | grep "===="
========== the
========== password
========== is
========== **********
```
- After retrieving the password, exited out of the SSH session and reconnected using the `bandit10` username and the newly obtained password to move on to the next level.

## Lessons Learned
I continued building my understanding of the pipe operator with using a new `strings` command in conjunction with a `grep` search. This taught me to learn how to filter and search in a non-binary file.
