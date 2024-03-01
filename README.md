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


## OUTPUT
![Screenshot (79)](https://github.com/KavinilavanDK/2a_Stop_and_Wait_Protocol/assets/144870429/86661307-186a-48be-adcd-abcb5ea42369)
![Screenshot (80)](https://github.com/KavinilavanDK/2a_Stop_and_Wait_Protocol/assets/144870429/ce10381e-66ed-4f83-8961-d0f8db6e3dff)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
