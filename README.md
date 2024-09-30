# 3a.CREATION FOR ECHO CLIENT AND ECHO SERVER USING TCP SOCKETS
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
Client
```
import socket


s = socket.socket()


s.bind(('localhost', 8000))


s.listen(5)


c, addr = s.accept()


address = {
    "165.165.80.80": "6A:08:AA:C2",
    "165.165.79.1": "8A:BC:E3:FA"
}

while True:
    
    ip = c.recv(1024).decode()
    
    try:
        
        c.send(address[ip].encode())
    except KeyError:
        
        c.send("Not Found".encode())

```

Serevr:
```
import socket


s = socket.socket()


s.connect(('localhost', 8000))

while True:
    
    ip = input("Enter logical Address (or type 'exit' to quit): ")
    
    if ip.lower() == 'exit':
        print("Exiting the program.")
        break
    
    
    s.send(ip.encode())
    
    
    mac_address = s.recv(1024).decode()
    
    
    print("MAC Address:", mac_address)

```
## OUPUT
Client
![Screenshot 2024-09-30 155214](https://github.com/user-attachments/assets/dac52c2e-a6f2-46e9-a6f1-9dc7bf18b1af)

Server
![Screenshot 2024-09-30 155228](https://github.com/user-attachments/assets/496ba748-2ced-4799-9b71-aae66eafeaf9)



## RESULT
Thus, the python program for creating Echo Client and Echo Server using TCP Sockets Links 
was successfully created and executed.
