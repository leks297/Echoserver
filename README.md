# Echoserver
Echo server and client using python socket
# AIM:

To develop an echo server and client using python socket.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:

### Server code
```
nano echoserver.py

import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    print("Server is listening...")
    conn, addr = s.accept()

    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
### Client code
```
nano echoclient.py

import socket

HOST = "127.0.0.1"
PORT = 65432

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"LEKHA SHREE R D,212225040197")
    data = s.recv(1024)

print(f"Received {data!r}")
```
### Run the Server
```
python3 echoserver.py
python3 echoclient.py
```

## OUTPUT:
### CLIENT OUTPUT:
<img width="1920" height="1080" alt="Screenshot (339)" src="https://github.com/user-attachments/assets/c0c4b8b6-2aae-4db1-b4fe-84de9981030d" />

### SERVER OUTPUT:
<img width="1920" height="1080" alt="Screenshot (340)" src="https://github.com/user-attachments/assets/fb2030e8-603a-45c6-a3ae-3a5ae89e0b9b" />


## RESULT:
The program is executed succesfully.
