# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

```
server.py
server.py
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("ARP Server is waiting...")
c, addr = s.accept()

ip_mac = {
    "192.168.1.1": "AA:BB:CC:DD:EE:01",
    "192.168.1.2": "AA:BB:CC:DD:EE:02",
    "192.168.1.3": "AA:BB:CC:DD:EE:03"
}

ip = c.recv(1024).decode()
print("Received IP Address:", ip)

if ip in ip_mac:
    c.send(ip_mac[ip].encode())
else:
    c.send("MAC Address not found".encode())

c.close()
s.close()

client.py
import socket

s = socket.socket()
s.connect(('localhost', 8000))

ip = input("Enter IP Address: ")
s.send(ip.encode())

mac = s.recv(1024).decode()
print("MAC Address:", mac)

s.close()

```
## OUTPUT

<img width="745" height="247" alt="image" src="https://github.com/user-attachments/assets/bee5c33f-c76c-4aa2-8725-25b091ae99a0" />

<img width="792" height="240" alt="image" src="https://github.com/user-attachments/assets/730f5ee9-47d6-4b9f-9e4b-f08afb9c28f7" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
