# EXP 2B : IMPLEMENTATION OF SLIDING WINDOW PROTOCOL:
## NAME : RUSHMITHA  R
## REGISTRATION NUMBER : 212224040281

## AIM:
To write a python program to perform Sliding window protocol and verify .

## ALGORITHM:

1. Start the program.

2. Get the frame size from the user

3. To create the frame based on the user request.

4. To send frames to server from the client side.

5. If your frames reach the server it will send ACK signal to client

6. Stop the Program

## PROGRAM :

### Server Side :

```
#server
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowlegement received from the server".encode())
```

### Client Side :

```
#client
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter window size : "))
st=0
i=0
while True:
    while(i<len(l)):
        st=st+s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i=i+s
```

## OUTPUT:

### Server Side :

<img width="1907" height="948" alt="2 b  server" src="https://github.com/user-attachments/assets/624164ae-3237-430c-8b4e-ae14b74afd8f" />


### Client Side : 

<img width="1911" height="1073" alt="2 b client" src="https://github.com/user-attachments/assets/173767e3-b75c-4c9c-b860-5063fc5d9d5e" />

## RESULT
Thus, python program to perform sliding window protocol was successfully executed
