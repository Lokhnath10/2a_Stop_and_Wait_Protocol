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
## CLIENT
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
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## CLIENT
![Screenshot 2024-03-05 213105](https://github.com/Lokhnath10/2a_Stop_and_Wait_Protocol/assets/138969918/92e66f7b-fe0b-4455-813b-5154c8a8096c)

## SERVER
![image](https://github.com/Lokhnath10/2a_Stop_and_Wait_Protocol/assets/138969918/64447681-90d5-49f6-bda8-31aa85940877)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
