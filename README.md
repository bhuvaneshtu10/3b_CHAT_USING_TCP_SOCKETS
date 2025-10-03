# 3b.CREATION FOR CHAT USING TCP SOCKETS
## AIM
To write a python program for creating Chat using TCP Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server
4. Send and receive the message using the send function in socket.
## PROGRAM
```
server.py

import socket

s = socket.socket()
s.bind(('127.0.0.1', 5002))
s.listen(1)
print("Server waiting...")

c, addr = s.accept()
print("Connected:", addr)

while True:
    msg = c.recv(1024).decode()
    if not msg or msg.lower() == "exit":
        break
    print("Client:", msg)
    reply = input("You: ")
    c.send(reply.encode())

c.close()
s.close()
```
```
client.py
import socket

s = socket.socket()
s.connect(('127.0.0.1', 5002))

while True:
    text = input("You: ")
    s.send(text.encode())
    if text.lower() == "exit":
        break
    reply = s.recv(1024).decode()
    print("Server:", reply)

s.close()

```
## OUPUT

<img width="711" height="223" alt="Screenshot 2025-10-03 080734" src="https://github.com/user-attachments/assets/b617ae47-30f6-4399-b7f5-7cebad1bfcd9" />

<img width="709" height="205" alt="Screenshot 2025-10-03 080742" src="https://github.com/user-attachments/assets/8b2dcf4e-85e2-44cd-92ef-f0eaf813989f" />

## RESULT
Thus, the python program for creating Chat using TCP Sockets Links was successfully 
created and executed.
