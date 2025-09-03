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
1.Server:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
2.Client:
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
## OUTPUT
1.Client:

<img width="500" height="196" alt="Screenshot 2025-09-03 105129" src="https://github.com/user-attachments/assets/2b548940-4850-4f05-a5cd-6ea570c21d6b" />

2.Server:

<img width="428" height="127" alt="Screenshot 2025-09-03 105142" src="https://github.com/user-attachments/assets/b24baa8d-f15e-4a7e-9374-b4e67a83cf63" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
