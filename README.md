# EX01 Developing a Simple Webserver
## Date:

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Revenue from Companies</h1>
<table border=2>
<tr>
<th> Company Name </th>
<th> Revenue </th>
<th> Financial Year </th>
</tr>

<tr>
<td> Microsoft </td>
<td> 86$ </td>
<td> 2014 </td>
</tr>

<tr>
<td> Oracle </td>
<td> 37$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> SAP </td>
<td> 20$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> VMware </td>
<td> 5.2$ </td>
<td> 2013 </td>
</tr>

<tr>
<td> CA Technologies </td>
<td> 4.7$ </td>
<td> 2013 </td>
</tr>

</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()



## OUTPUT:

![Screenshot 2025-05-12 204654](https://github.com/user-attachments/assets/e140f605-adf7-482c-8907-58cdea0ba365)
![Screenshot 2025-05-12 204636](https://github.com/user-attachments/assets/eb5241bb-edb2-43cd-9f19-1e96bd533e10)

## RESULT:
The program for implementing simple webserver is executed successfully.
