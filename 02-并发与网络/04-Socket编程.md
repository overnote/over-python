## 一 Socket简介

### 1.1 udp
Socket简称套接字，是不同主机间进程通信的方式。

UDP服务端：
```py
import socket

# 创建UDP套接字
s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

# 绑定本地信息，不绑定则随机分配
s.bind(('127.0.0.1', 8080))

# 接收数据
while True:
    data = s.recvfrom(1024)
    print(data)

# 关闭套接字
s.close()
```

UDP客户端:
```py
import socket

# 创建UDP套接字：第一个参数代表IPV4，第二个参数代表是UDP还是TCP
s = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)

# 套接字发送数据
num = 1
while True:
    data = 'hello' + str(num)
    # s.sendto('hello', ('127.0.0.1', 8080))
    s.sendto(data.encode('utf-8'), ('127.0.0.1', 8080))
    num = num + 1
    if num == 10:
        break

# 关闭套接字
s.close()
```
### 1.2 TCP

TCP服务端：
```py
import socket

# 创建UDP套接字
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# 绑定服务器
s.bind(('', 8080))

# socket创建的套接字属性默认是主动的，listen变为被动，用来接收客户端信息
s.listen(128)

# 不断循环接收不同客户端的连接
while True:
    # 等待到来
    rec_client, rec_addr = s.accept()
    print(rec_addr)

    # 接收数据
    data = rec_client.recv(1024)
    print(data)

    # 发送数据
    rec_client.send('accept..'.encode('utf-8'))

    # 关闭套接字
    rec_client.close()

```

TCP客户端：
```py
import socket

# 创建TCP
s = socket.socket(socket.AF_INET, socket.SOCK_STREAM)

# 连接服务器
s.connect(('127.0.0.1', 8080))

# 套接字发送数据
num = 1
while True:
    data = 'hello' + str(num)
    rec = s.send(data.encode('utf-8'))
    print(rec)
    num = num + 1
    if num == 10:
        break

# 关闭套接字
s.close()
```