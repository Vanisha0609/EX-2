# EX-2 IMPLEMENTATION OF STOP AND WAIT PROTOCOL

DATE:16/03/2023

## AIM :
To write a python program to perform stop and wait protocol

## ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
otherwise it will sendNACK signal to client.
6. Stop the program

## PROGRAM :

CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
 i=input("Enter a data: ")
 c.send(i.encode())
 ack=c.recv(1024).decode()
 if ack:
  print(ack)
  continue
 else:
  c.close()
  break
 ```
 SERVER:
 ```
 import socket
 s=socket.socket()
 s.connect(('localhost',8000))
 while True:
  print(s.recv(1024).decode())
  s.send("Acknowledgement Recived".encode())
 ```
## OUTPUT :

CLIENT:

![swpcl](https://github.com/Vanisha0609/EX-2/assets/119104009/bea5315f-b49d-4a0a-83c8-2150db710e3a)

SERVER:

![swps](https://github.com/Vanisha0609/EX-2/assets/119104009/f4b9b174-e6ca-4f2e-8169-6c0a55b3c33f)

## RESULT :
  Thus, python program to perform stop and wait protocol was successfully executed


