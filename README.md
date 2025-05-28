# EX01 Developing a Simple Webserver
## Date:03.05.2025

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
Serving the HTML pages.

### Step 5:
Testing the webserver.

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
![alt text](<Screenshot (41).png>)
![alt text](<Screenshot (42).png>)


## RESULT:
The program for implementing simple webserver is executed successfully.
