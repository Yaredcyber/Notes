# Socket Commands   🔌

- **socket.socket()**: Creating socket
- **s.bind(host, port)**: Binding socket to a specific host and port
- **s.listen()**: Listening for incoming connections
- **s.accept()**: Accepting incoming connections
- **s.send()**: Sending data through the socket
- **s.recv()**: Receiving data from the socket
- **s.close()**: Closing the connection

# Creating Socket on Server

```python
import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
port = 8080
s.bind((socket.gethostname(), port))
print("Binding the connection on port:", port)
s.listen(5)

while True:
    connection, address = s.accept()
    print("Connection established from:", address)
    connection.send(bytes("Hello there! This is the hosted server", "utf-8"))
    connection.close()
```

## Explanation

- **socket**: Python module used to establish connections between computers.
- **AF_INET**: Specifies the IPv4 address family.
- **SOCK_STREAM**: Indicates the use of TCP, a reliable protocol for data transmission.
- **s.accept()**: Accepts incoming connections and returns a tuple (`connection`, `address`).
- **connection**: Object representing the connection with the client.
- **address**: IP address of the client.
- **connection.send()**: Sends data from server to client after encoding it into bytes using `"utf-8"`.
- **bytes**: Converts strings/characters, numbers, and floats into bytes for
network transmission using the UTF-8 encoding.
- **socket.gethostname()**: Used to assign owr private ip adress
- **connection.close()**: Closes the connection with the client.

<details>
  <summary style="background-color: lightgreen; padding: 5px; border-radius: 5px; font-size: 28px;font-style:bold; cursor: pointer;">bind()</summary>

```python

s.bind((ip_address, port))
```
</details>
<hr>
<details>
  <summary style="background-color:green; padding: 5px; border-radius: 5px; font-size: 18px; cursor: pointer;">listen()</summary>

```python

s.listen(5)
```
>- Listen the incomming connections
</details>

# Creating Socket on Client

```python

import socket

s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
port = 8080
s.connect((socket.gethostname(), port))
msg = s.recv(1024)  # Receiving up to 1MB of data
print(msg.decode("utf-8"))  # Decoding the received data from the server
```

# Explanation

<details>
  <summary style="background-color: blue; padding: 5px; border-radius: 5px; font-size: 18px; cursor: pointer;">connect()</summary>

```python
s.connect((ip_address, port))
```
>- Used to connect client to serever by using port and ip adress
</details>
<hr>
<details>
  <summary style="background-color: lightgreen; padding: 5px; border-radius: 5px; font-size: 18px; cursor: pointer;">recv()</summary>

```python

msg = s.recv(buffer_size)
```
>- buffer_size: Specifies the maximum amount of data to receive.
>- Returns data in bytes format.
>- Blocking function, meaning it waits until data is received.



</details>






## summary 🗒

| Server Command | Explanation |
| -------------- | ----------- |
| `bind`         | Binds the socket to a specific IP address and port number. This is necessary before the socket can receive connections. Example: `s.bind((ip_address, port))` |
| `listen`       | Listens for incoming connections from clients. It specifies the maximum number of queued connections that can be waiting for acceptance. Example: `s.listen(5)` |
| `accept`       | Accepts an incoming connection. This function blocks until a connection is received and returns a new socket object representing the connection and the address of the client. Example: `connection, address = s.accept()` |
| `close`        | Closes the socket connection on the server side. It releases the socket resources and stops listening for new connections. Example: `s.close()` |
| `send`         | Sends data from the server to the connected client. The data must be encoded into bytes before sending. Example: `connection.send(bytes(data, 'utf-8'))` |

| Client Command | Explanation |
| -------------- | ----------- |
| `connect`      | Initiates a connection to a remote server. It requires the server's IP address and port number. Example: `s.connect((server_ip, server_port))` |
| `recv`         | Receives data from the server. It blocks until data is received or the connection is closed. The argument specifies the maximum amount of data to receive at once. Example: `data = s.recv(buffer_size)` |

