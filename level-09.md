# Level 8 -> Level 9
## Objective:
The password is located in a file named `data.txt` within the home directory. The password is the only line of text that appears once. The password will be used to log into `bandit9`.

## Key Concepts & Commands:
- `sort`: Arranges lines of text files in a given order. By default, it sorts alphabetically.
- `uniq`: Reports or omits repeated adjacent lines.
- `uniq -u`: Prints only unique lines.
- `|`: The pipe operator passes out the output of one command directly into another command.
  
## Investigation & Troubleshooting 
- The `data.txt` file contains many duplicate entries of possible passwords.
- Needed a method to isolate the only non-duplicated line.
- Noticed in `man uniq` an example of how to display only unique lines.

```bash
 Display only unique lines:

sort path/to/file | uniq [-u|--unique]
```
- Used this example format to find the one unique line.

```bash
bandit8@bandit:~$ sort data.txt | uniq -u
***********
```
- Discovered this `|` operator can pass one command output to another.
After retrieving the password, exited out of the current SSH session and used the `bandit9` credentials along with the new password to move on to the next level.

## Lessons Learned
I learned new command tools such as `uniq` and `sort`, along with the `|` operator, to identify the only unique line in a file. I also learned since `uniq` only compares each adjacent duplicate line, that sorting the file first was necessary.
