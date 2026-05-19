# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

## CLIENT.PY
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
while(i<len(l)): st+=s
c.send(str(l[i:st]).encode())
ack=c.recv(1024).decode()
if ack:
print(ack)
i+=s

```
## SERVER.PY
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
SAVEETHA ENGINEERING COLLEGE
while True:
print(s.recv(1024).decode())
s.send("acknowledgement recived from the server".encode())
```

## OUPUT

server
<img width="641" height="91" alt="Screenshot 2026-05-19 101552" src="https://github.com/user-attachments/assets/ad3e4d5a-e345-461b-8b03-22beb429d863" />

client
<img width="445" height="123" alt="Screenshot 2026-05-19 101628" src="https://github.com/user-attachments/assets/4a4596e4-bd62-4270-b9ff-336eb694e21f" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
