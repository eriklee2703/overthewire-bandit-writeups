# Level 13 -> Level 14
## Objective:
Locate and use the provided private SSH key to authenticate as `bandit14`. The password is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. 

## Key Concepts & Commands:
- `ssh -i`: This tells SSH which private key file to use for authentication when connecting to a remote server.
- `nano`: A text editor used to create or edit files.
- `chmod 600`: Sets file permission so only the owner of a file can read and write.

## Investigation & Troubleshooting 
- Unlike previous levels where a password is found in a file, this level provides a private SSH key needed to authenticate as the next user.
- Displayed the contents of the `sshkey.private` key and copied the key.
- Exited out of the `bandit13` session to create a file locally on my Mac.
- Created a file for the SSH key using the Nano text editor and pasted the contents.
- After saving the SSH key file to my local folder, needed to adjust the file permissions since SSH requires a private key file to have restricted permissions.
- Used `chmod 600 sshkey.private` to edit the existing permissions so that only the user has read and write access.
- Used `ssh -i` to specify the file used for authentication to connect to `bandit14`.

```bash
nano sshkey.private
chmod 600 sshkey.private
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
```

## Lessons Learned
I learned how to use key-based authentication through SSH. I also learned about the `nano` command which is used to create and edit a file along with `chmod` which is used to manage file permissions.
