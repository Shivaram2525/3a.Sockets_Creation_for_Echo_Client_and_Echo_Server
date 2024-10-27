# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS

## Name: SHIVARAM M.
## Reg.NO.: 212223040195


# AIM
To write a python program for creating Echo Client and Echo Server using TCP
Sockets Links.
## ALGORITHM:
1. Import the necessary modules in python
2. Create a socket connection to using the socket module.
3. Send message to the client and receive the message from the client using the Socket module in
 server .
4. Send and receive the message using the send function in socket.
## PROGRAM
```
# Client
import socket

HOST = '127.0.0.1'  
PORT = 65432    

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as client_socket:
    client_socket.connect((HOST, PORT))
    message = input("Enter message to send to the server: ")
    client_socket.sendall(message.encode())  
    
    data = client_socket.recv(1024)
    print('Received from server:', data.decode())

```
```
# Server
import socket

HOST = '127.0.0.1'  
PORT = 65432        

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as server_socket:
    server_socket.bind((HOST, PORT))
    server_socket.listen()
    print(f'Server listening on {HOST}:{PORT}...')
    
    conn, addr = server_socket.accept()
    with conn:
        print(f'Connected by {addr}')
        while True:
            data = conn.recv(1024)
            if not data:
                break

            conn.sendall(data)

```

## OUPUT
<img width="1680" alt="Echo_Client_Server" src="https://github.com/user-attachments/assets/bf487fc3-b2b4-44ea-a388-b64ab839e94f">

## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
