# Level 6 -> Level 7
## Objective:
Locate the password stored somewhere on the server containing all of the following properties: owned by user `bandit7`, owned by group `bandit6`, and 33 bytes in size.

## Key Concepts & Commands:
- `find -size`: Searches for files with the specified size.
- `find -user`: Matches files based on their user ownership.
- `find -group`: Matches files based on their group ownership.
- `2>/dev/null`: Redirects standard error messages.

## Investigation & Troubleshooting 
- This problem continues building on the `find` command and exploring different options.
- After consulting the `man` page and researching online, discovered the `-user` and `-group` options, which can be used to specify the user and group owners.
- Similarly to the previous level, used `-size 33c` to search for files exactly 33 bytes in size.
- Trivial, but also realized that the home directory is a subdirectory of root directory. So shifted the search line to the root directory with `cd /`.
- Initially, the first search was still cluttered with numerous "Permission Denied" messages.
- To filter this out, used `2>/dev/null` which redirects all the error messages in the terminal to `/dev/null`.

```bash
bandit6@bandit:/$ find -size 33c -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
```
- Located the password file for `bandit7` which was stored deep within the directory tree.

```bash
bandit6@bandit:/$ cat /var/lib/dpkg/info/bandit7.password
```
- Retrieved the password by pasting the entire absolute path into `cat` without having to change directories.
- After retrieving the password, exited out of the current session and reconnected using the `bandit7` username and the new password to move on to the next level.

## Lessons Learned
I continued to explore different `find` options and also learned how to handle standard error messages by redirecting them with `2>/dev/null`, making command-line searches much cleaner.
