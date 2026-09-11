# Bandit Level 19-20 

### Objective: 
The objective of this level is to find the password by using the [set-uid](#concepts-learned-) binary that is given in the home directory. 

### Steps Taken: 
1. Connect to the remote server(bandit.labs.overthewire.org -p 2220) using ssh command as user bandit19, at port 2220.
``` bash
ssh bandit19@bandit.labs.overthewire.org -p 2220
```
2. Run the given setuid binary without an argument to understand how it works.
```bash 
./bandit20-do 
```
**Output**: 
```bash
Run a command as another user.
  Example: ./bandit20-do whoami
```
Thus, the binary lets us run any command as the user bandit20. 

3. Extract the password from the file /etc/bandit_pass/bandit20 using the cat command as argument. 
```bash
./bandit20-do cat /etc/bandit_pass/bandit20 
```
### Commands Used: 
cat 

### Concepts Learned: 
##### What is a setuid binary??
"Setuid Binary" is made up of two words, setuid and binary. The word setuid refers to a permission in Unix-like operating system. It lets a user to run an executable program as the owner of the executable program. 
Binary refers to a file that has been compiled and ready for execution by the Operating System. 
In the context of this level, the bandit20-do setuid binary lets us run commands as the user bandit20. Therefore, we can read the password for the next level that can only be accessed by the user bandit20. 
