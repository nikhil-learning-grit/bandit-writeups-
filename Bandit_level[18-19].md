# Bandit Level 18-19 

### Objective: 
The objective of this level is to retrieve the password from the file readme in the home directory of the remtoe host. The condition here is that the .bashrc has been configured to log out immediately if someone tries to login. 

### Steps Taken: 
1. Due to configuration of the .bashrc, we are logged out of the server as soon as we log in. Therefore we will define the command to be executed commands inside the remote host using the ssh command (using the username bandit18 and the password retreived in the previous level.)
```bash
ssh bandit18@bandit.labs.overthewire.org -p "cat readme" 
```
### Commands Used: 
1. ssh

### Concepts Learned: 
**Executing commands externally in a remote server using ssh commands:** If the command to be executed in the remote server is explicitly mentioned with the ssh command using double quotes (" "), the remote server executes it as soon as we log in to the server. 
So, in the context of this level, since we are getting logged out as soon as we log in, mentioning the commands in double quotes with the ssh command executes the required command ("cat readme") before the server logs us out. Thus, we have retrieved the password for the next level. 