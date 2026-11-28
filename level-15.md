# Level 14 -> Level 15

## Objective:
Use the password stored in `/etc/bandit_pass/bandit14` and submit to port 30000 on `localhost` to retrieve the next password.

## Key Concepts & Commands:
- `nc`: Netcat is a utility that reads and writes raw data across network connections using TCP or UDP. 

## Investigation & Troubleshooting 
- To connect to port 30000 on the `localhost`, used `nc localhost 30000`, which establishes a TCP connection to the listening service.
- The service listens for incoming connections, expecting for the current `bandit14` password where in return will retrieve the next level password if correct.

```bash
bandit14@bandit:/$ nc localhost 30000
***********
Correct!
***********
```
- After retrieving the password, exited out of the current session and reconnected using the `bandit15` username and the new password to move on to the next level.

## Lessons Learned
I learned to connect to communicate with a network service using Netcat through a specific TCP port. I also learned the purpose of `localhost` which allows a computer to communicate with itself.
