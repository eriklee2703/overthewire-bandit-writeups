# Level 11 -> Level 12
## Objective:
The password is stored in the `data.txt` file, where all lowercase and uppercase letters have been rotated thirteen positions.
## Key Concepts & Commands:
- `tr`: The translitertion command is used to translate, replace, or delete specific characters from standard input.
- `<` Redirects a file's content into a command as standard input.

## Investigation & Troubleshooting 
- The `data.txt` file contains text that has been shifted thirteen positions with the `ROT13` cipher.
- Used the `tr` command to reverse the character substituion inputs to decode the text.
```bash
cat data.txt
Gur cnffjbeq vf TEBbmJCB8DlA0zTewHxVQ0JPLxMvDkeA

bandit11@bandit:~$ tr 'a-zA-Z' 'n-za-mN-ZA-M' < data.txt
The password is *******************

```
- It took sometime to understand the `tr` command, but realized that the first and second character sets need to match in total corresponding characters.
- Unlike commands such as `grep`, `tr` needs `<` operator since it reads from standard input.
- After retrieving the password, exited out of the current session and reconnected using the `bandit8` username and the new password to move on to the next level.

## Lessons Learned
I learned how to use `tr` to decode a line that has been shifted thirteen positions using `ROT13`. This command can also be used to remove or translate characters.
