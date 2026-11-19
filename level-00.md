# Level 0
## Objective:
Log into OverTheWire Bandit server (`bandit.labs.overthewire.org`) on port 2220 using the starting credentials (`bandit0` / `bandit0`) via SSH. 

## Key Concepts & Commands:
- `ssh` (Secure Shell): Enables you to securely control another computer through the command line.
- `bandit0`: This is the username you are logging in as.
- `@`: Separates the user from the hostname/server (IP address can also be used as the hostname).
- `bandit.labs.overthewire.org`: The hostname (domain address) of the remote computer.
- `-p 2220`: Tells the computer to connect to port 2220.

## Investigation & Troubleshooting 
- To login remotely through ssh, you need to understand the general command format:
```bash

   ssh <username>@<server-address> -p <port-number>

```
- Password characters are not displayed when typing into the SSH password prompt. This is intentional and helps protect passwords from being observed by others.

## Lessons Learned
SSH also intentionally hides password input for security reasons, such as preventing shoulder surfing.
