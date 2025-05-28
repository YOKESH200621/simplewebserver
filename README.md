# EX01 Developing a Simple Webserver
## Date:23-05-2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Suite</title>
</head>
<body>
    <h1>Protocols in the TCP/IP Protocol Suite</h1>
    <ul>
        <li>Application Layer: HTTP, FTP, SMTP, DNS, Telnet, SNMP</li>
        <li>Transport Layer: TCP, UDP</li>
        <li>Internet Layer: IP, ICMP, IGMP, ARP</li>
        <li>Network Access Layer: Ethernet, Wi-Fi, PPP</li>
    </ul>
</body>
</html>

"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:

![Screenshot (55)](https://github.com/user-attachments/assets/dcde8f31-44fa-468d-8e9c-f11a6a8e2694)

![Screenshot (56)](https://github.com/user-attachments/assets/1902ae96-5680-4a3a-9dfb-d26cb197b98c)


## RESULT:
The program for implementing simple webserver is executed successfully.
