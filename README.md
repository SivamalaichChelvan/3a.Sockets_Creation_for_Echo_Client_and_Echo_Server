# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
```
client.py

import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    msg=input("Client > ")
    s.send(msg.encode())
    if msg=="exit":
        print("Disconnected")
        break
    print("Server >", s.recv(1024).decode())
s.close()
```
```
server.py

import socket
s=socket.socket()
s.bind(('localhost', 8001))
s.listen(1)
print("Waiting for connection...")
c, addr=s.accept()
print("Connected to", addr)
while True:
    clientMessage=c.recv(1024).decode()
    if clientMessage=="exit":
        print("Client disconnected")
        break
    print("Client >", clientMessage)
    reply = input("Server > ")
    c.send(reply.encode())
c.close()
s.close()
```
## OUPUT
<img width="973" height="256" alt="image" src="https://github.com/user-attachments/assets/ce8a2a53-732c-4bd8-8e43-f6d3b7c5a7cd" />
<img width="936" height="277" alt="image" src="https://github.com/user-attachments/assets/e03caab1-9dd4-4d8a-a3ca-2fe5dd6a4e0d" />

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
