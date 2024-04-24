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
## CLIENT:
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
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## OUTPUT
## CLIENT:
![image](https://github.com/hanshika-773/2a_Stop_and_Wait_Protocol/assets/153576501/69db9c9c-3b7e-43cc-a090-87d54e85cc78)

## SERVER:
![image](https://github.com/hanshika-773/2a_Stop_and_Wait_Protocol/assets/153576501/9c2866a5-95fa-4271-a6d6-6a2305f83b7e)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
