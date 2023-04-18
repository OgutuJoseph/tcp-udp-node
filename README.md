# Project Resources

https://www.youtube.com/watch?v=1acKGwbby-E

# Tech Differences
## TCP
### Pros
-Acknowledgement
-Guaranteed delivery
-Connection based
-Congestion control
-Ordered packets
### Cons
-Larger packets
-More bandwidth
-Slower than UDP
-Stateful
-Server memory (DOS)
### Usage
-Start debugging the file; output will be viewed on 'DEBUG CONSOLE'
-Get a (wsl) terminal then run telnet 127.0.0.1 8080
-On the above terminal you will see connection established
-You can then send info through the same terminal e.g. type 'Hi' then 'Enter'
-A ::breakpoint on the log:: returns 4 bytes
-0 :: 72    :: h
-1 :: 105   :: 1
-2 :: 13    :: carriage return
-3 :: 10    :: carriage return
-On killing the debugging session you get a message: 'Connection closed by foreign host'
-On attempting to send more data it's not successful, illustrating the 'stateful' nature of the protocol.

## UDP
### Pros
-Smaller packets
-Less bandwidth
-Faster than TCP
-Stateless
### Cons
-No acknowledgement
-No guaranteed delivery
-Connectionless
-No Congestion control
-No Ordered packets
-Security
### Usage
-Start debugging the file; output will be viewed on 'DEBUG CONSOLE'
-Get a (wsl) terminal then run echo 'hi' | nc -w1 -u 127.0.0.1 8081
-A ::breakpoint on the log:: returns 3 bytes
-0 :: 104   :: h
-1 :: 105   :: i
-2 :: 10    :: carriae return