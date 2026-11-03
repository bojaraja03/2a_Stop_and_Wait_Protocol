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
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()
```
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()
```
## OUTPUT
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/cb840b0f-6bd2-4897-a5a9-93a22d7017be" />
<img width="1920" height="1020" alt="image" src="https://github.com/user-attachments/assets/18c79750-bc3d-4fd7-bbad-7fe381dabf0a" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
