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
ex2as.py
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()

while True:
    i=input("Enter a data:")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

ex2ac.py
```
import socket
s=socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```

## OUTPUT

<img width="1481" height="759" alt="Screenshot 2025-09-13 161115" src="https://github.com/user-attachments/assets/28866b28-bf34-420e-8700-5ff5ffa9a80a" />



<img width="1483" height="765" alt="Screenshot 2025-09-13 161139" src="https://github.com/user-attachments/assets/70dd691f-8c4f-4cfd-b42e-0975cfb30bec" />



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
