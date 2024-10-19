# 2c.SIMULATING ARP /RARP PROTOCOLS
## Name:SHYAM SUJIN U
## Reg No.212223040201
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP:
```
import socket
s=socket.socket()
s.bind(('localhost',8880))
s.listen(5)
c,addr=s.accept()
address={"192.168.144.56":" AC:50:DE:1D:05:A3"};
while True:
    ip=c.recv(1024).decode()
    try:
        c.send(address[ip].encode())
    except KeyError:
        c.send("Not Found".encode())
```
## OUPUT - ARP:
![Screenshot (80)](https://github.com/user-attachments/assets/f4e9ac50-56ca-4858-8045-dbd0460a9ba5)


## PROGRAM - RARP:
```
import socket
s=socket. socket()
s.connect(('localhost',8880))
while True:
    ip=input("Enter logical Address : ")
    s. send (ip. encode())
    print ("MAC Address",s. recv(1024) . decode ())
```
## OUPUT -RARP:
![Screenshot (79)](https://github.com/user-attachments/assets/fefb53f3-6d5a-4258-80fc-650158a3883a)


## RESULT:
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
