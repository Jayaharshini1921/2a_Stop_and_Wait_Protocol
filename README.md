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
server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode()) 
```
client:
```
import socket 
s=socket.socket() 
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

## OUTPUT
server:
![Screenshot 2025-04-12 090319](https://github.com/user-attachments/assets/f1617082-7e6d-4488-91bb-fb2ab9cde79e)

client:
![Screenshot 2025-04-12 090306](https://github.com/user-attachments/assets/e871f93d-91d4-4a29-aeb9-61bbbceccbfb)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
