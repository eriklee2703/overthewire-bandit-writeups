# Level 10 -> Level 11
## Objective:
The password is stored in a `data.txt` file which is encoded in `base64`.

## Key Concepts & Commands:
- `base64`: Encodes data in base64.
- `base64 -d`: Decodes data in base64.

## Investigation & Troubleshooting 
- The `data.txt file contains a single line of encoded text.
- `base64 -d` decodes base64 encoded text.

```bash
cat data.txt
VGhlIHBhc3N3b3JkIGlzIHBZZk9ZNkh3VXNEajVyTDlVdnloVTdNQ212OHZONVJvCg==
bandit10@bandit:~$ base64 -d data.txt
The password is *************
bandit10@bandit:~$ cat data.txt
```
- After retrieving the password, exited out of the current session and reconnected using the `bandit11` username and the new password to move on to the next level.

## Lessons Learned
I learned to encode and decode base64 text.
