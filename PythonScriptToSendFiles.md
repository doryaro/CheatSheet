# Send file with python script using server-clinet: 



### server.py:
~~~import socket

# Server settings
HOST = '0.0.0.0'
PORT = 65432
BUFFER_SIZE = 1024

def receive_file(filename, conn):
    with open(f"C:\Users\OtherUser\Desktop\<des_file>", 'wb') as f:
        while True:
            data = conn.recv(BUFFER_SIZE)
            if not data:
                break
            f.write(data)

def main():
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.bind((HOST, PORT))
        s.listen()
        print(f"Server started on {HOST}:{PORT}")

        conn, addr = s.accept()
        with conn:
            print('Connected by', addr)
            filename = conn.recv(BUFFER_SIZE).decode('utf-8')
            conn.sendall(b"ACK")  # acknowledge filename reception
            receive_file(filename, conn)

if __name__ == "__main__":
    main()
~~~


### client.py:

~~~import socket

# Server settings
SERVER_HOST = ''  # IP of the Server
PORT = 65432
BUFFER_SIZE = 1024

def send_file(filename):
    with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
        s.connect((SERVER_HOST, PORT))
        s.sendall(filename.encode('utf-8'))
        # Wait for acknowledgment
        s.recv(BUFFER_SIZE)

        with open(filename, 'rb') as f:
            while True:
                data = f.read(BUFFER_SIZE)
                if not data:
                    break
                s.sendall(data)

def main():
    filename = f"C:\Users\DorYaron\Desktop\...<filename>"
    send_file(filename)

if __name__ == "__main__":
    main()
~~~


