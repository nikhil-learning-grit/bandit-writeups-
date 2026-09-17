# Bandit Level 20-21 

### Objective: 
The objective of this level is to retrieve the password using the setuid provided in the home directory. 

### Steps Taken: 
1. Connect to the remote server (bandit.labs.overthewire.org) at port 2220, with username bandit20. 
```bash
ssh bandit20@bandit.labs.overthewire.org -p 2220
```
2. Run the setuid binary without an argument to understand how it works
```bash
./suconnect 
```
Output: 
```bash
Usage: ./suconnect <portnumber>
This program will connect to the given port on localhost using TCP. If it receives the correct password from the other side, the next password is transmitted back.
```
Thus, from the output, we can understand that the setuid binary sets up a TCP connection with a local host at the specified port, and if it recieves the password of the current level from the other side, it sends the password for the next level. 
The following steps will be used to do the same and retrieve the password.

3. Set up a server listening on local host at any port number of your choice, given that it is not being used by any other service. For instance, we're using the port number 1234 in this level. 
```bash
nc -l localhost 1234 
```
4. Use the given setuid binary to connect to the localhost on the same port (1234).
```bash
./suconnect 1234
```
**Note:** For performing step 3 and step 4 simultaneously on one screen, multiple terminal sessions were opened using the tmux command (terminal multiplexer) followed by the pressing (Ctrl + B + " (shift + ')).

5. On the listening terminal, type the password of the current level and press enter. It thus displays the password for the next level. 

### Commands Used: 
1. tmux
2. nc

### Concepts Learnt: 
1. Operating multiple terminal sessions using a single screen. The tmux command followed and pressing (Ctrl + B) and then the corresponding option creates a separate terminal session for us. For creating a terminal session vertically, we can use (Ctrl + B + ") whereas for creating multiple sessions horizontally, we can use (Ctrl + B + :).
2. Setting up a listening port using nc. The -l flag in the nc command helps us set up a listening port at the given hostname and port. Thus, nc is efficient to connect devices directly over TCP protocol. 