# EX-6 IMPLEMENTATION OF PING COMMAND

## DATE :12-04-2023

## AIM :
To write the python program for simulating ping command.
## ALGORITHM :
```
1. Start the program.
2. Include necessary package in java.
3. To create a process object p to implement the ping command.
4. Declare one Buffered Reader stream class object.
5. Get the details of the server
6. Length of the IP address.
7. Time required to get the details.
8. Send packets, receive packets and lost packets.
9. Minimum, maximum and average times.
10. Print the results.
11. Stop the program.
```
## PROGRAM :
```
Developed By: Yashaswi Mitta
Reg No: 212221230062
```
### client:
```
import socket
from pythonping import ping
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    hostname=c.recv(1024).decode()
    try:
        c.send(str(ping(hostname, verbose=False)).encode())
    except KeyError:
        c.send("Not Found".encode())
```
### server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter the website you want to ping ")
    s.send(ip.encode())
    print(s.recv(1024).decode())
```
## OUTPUT:
![cn 6-1](https://github.com/yashaswimitta/EX-6/assets/94619247/60d6d47a-d95b-4a0a-b777-06454572733e)

![cn 6-2](https://github.com/yashaswimitta/EX-6/assets/94619247/b775d5a1-d3e4-41f4-b795-2affeb23f19a)



## RESULT:
Thus, the python program for simulating ping command was successfully executed.
