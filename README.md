# PX-Server
Easy and lightweight web server coded in C, woking for Linux systems.

# Using Information

Complie:
```
gcc server.c -o Server | gcc web.c -o WebServer
```
Give executable and root ownership:
```
chmod u+s ./Server | chmod u+s ./Server

chown root ./Server | chown root ./WebServer
```
Run the webserver with:
```
./WebServer
```
You can also see the traffic int that port by running the server:
```
./Server
```

By default, the web server is running in the port 80 and the root directory containing the web code is:
```
/var/www/html
```

This can be changed by editing this lines.
Web server(Lines 12 and 13):
```c
#define PORT 80   
#define WEBROOT "/var/www/html" 
```

Server(Line 9):
```c
#define PORT 80 
```

Both can't be running at the same time in the same port.
```
[!!] Fatal Error binding to socket: Address already in use
```

Kill the process by running:
```
fuser -k 8080/tcp
```

# Web Server Output

WebServer:
```
Accepting web requests on port 80

Accepting web requests on port 80
Got request from 127.0.0.1:41078 "GET / HTTP/1.1"
	Opening '/var/www/html/index.html'	 200 OK
Got request from 127.0.0.1:41080 "GET /image.jpg HTTP/1.1"
	Opening '/var/www/html/image.jpg'	 200 OK
Got request from 127.0.0.1:41082 "GET /image.jpg"
```

Server:

```
Server: conection detected from 127.0.0.1 port 41084
RECV: 439 bytes
47 45 54 20 2f 20 48 54 54 50 2f 31 2e 31 0d 0a | GET / HTTP/1.1..
48 6f 73 74 3a 20 6c 6f 63 61 6c 68 6f 73 74 0d | Host: localhost.
0a 55 73 65 72 2d 41 67 65 6e 74 3a 20 4d 6f 7a | .User-Agent: Moz
69 6c 6c 61 2f 35 2e 30 20 28 58 31 31 3b 20 55 | illa/5.0 (X11; U
62 75 6e 74 75 3b 20 4c 69 6e 75 78 20 78 38 36 | buntu; Linux x86
5f 36 34 3b 20 72 76 3a 31 30 30 2e 30 29 20 47 | _64; rv:100.0) G
65 63 6b 6f 2f 32 30 31 30 30 31 30 31 20 46 69 | ecko/20100101 Fi
72 65 66 6f 78 2f 31 30 30 2e 30 0d 0a 41 63 63 | refox/100.0..Acc
65 70 74 3a 20 74 65 78 74 2f 68 74 6d 6c 2c 61 | ept: text/html,a
70 70 6c 69 63 61 74 69 6f 6e 2f 78 68 74 6d 6c | pplication/xhtml
2b 78 6d 6c 2c 61 70 70 6c 69 63 61 74 69 6f 6e | +xml,application
2f 78 6d 6c 3b 71 3d 30 2e 39 2c 69 6d 61 67 65 | /xml;q=0.9,image
2f 61 76 69 66 2c 69 6d 61 67 65 2f 77 65 62 70 | /avif,image/webp
2c 2a 2f 2a 3b 71 3d 30 2e 38 0d 0a 41 63 63 65 | ,*/*;q=0.8..Acce
70 74 2d 4c 61 6e 67 75 61 67 65 3a 20 65 6e 2d | pt-Language: en-
55 53 2c 65 6e 3b 71 3d 30 2e 35 0d 0a 41 63 63 | US,en;q=0.5..Acc
65 70 74 2d 45 6e 63 6f 64 69 6e 67 3a 20 67 7a | ept-Encoding: gz
69 70 2c 20 64 65 66 6c 61 74 65 2c 20 62 72 0d | ip, deflate, br.
0a 43 6f 6e 6e 65 63 74 69 6f 6e 3a 20 6b 65 65 | .Connection: kee
70 2d 61 6c 69 76 65 0d 0a 55 70 67 72 61 64 65 | p-alive..Upgrade
2d 49 6e 73 65 63 75 72 65 2d 52 65 71 75 65 73 | -Insecure-Reques
74 73 3a 20 31 0d 0a 53 65 63 2d 46 65 74 63 68 | ts: 1..Sec-Fetch
2d 44 65 73 74 3a 20 64 6f 63 75 6d 65 6e 74 0d | -Dest: document.
0a 53 65 63 2d 46 65 74 63 68 2d 4d 6f 64 65 3a | .Sec-Fetch-Mode:
20 6e 61 76 69 67 61 74 65 0d 0a 53 65 63 2d 46 |  navigate..Sec-F
65 74 63 68 2d 53 69 74 65 3a 20 6e 6f 6e 65 0d | etch-Site: none.
0a 53 65 63 2d 46 65 74 63 68 2d 55 73 65 72 3a | .Sec-Fetch-User:
20 3f 31 0d 0a 0d 0a                            |  ?1....
```

# Images

Web Server:

![image](https://user-images.githubusercontent.com/84512017/172027947-0bf85f4a-f60f-4411-9cba-6efbe32a2b54.png)

![image](https://user-images.githubusercontent.com/84512017/172027963-dc56c2a2-b7dc-450b-ad2b-6c3923e10c94.png)

Server:

![image](https://user-images.githubusercontent.com/84512017/172027983-f16f9051-30c0-46fe-bd23-c0c474349d64.png)

# HTML

```html
<html>
<head><title>Example site</title></head>
<body bgcolor="#000000" text="#ffffffff">
<center>
<h1></h1>
<br>
<br>
<br>
<img src="image.jpg"><br>
</center>
</body>
</html>
```
