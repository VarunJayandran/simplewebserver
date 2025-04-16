# EX01 Developing a Simple Webserver
## Date: 09/04/2025
## NAME: VARUN J C
## REG NO : 212224240179
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
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<html>
<head>
<title>Top Software Industries</title>
</head>
<body>
<table border="1" cellspacing="10" cellpadding="6">
<caption>Top 5 Revenue Generating Software Companies</caption>
<tr>
<th>S.no</th>
<th>Companies</th>
<th>Revenue</th>
</tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>43 billion</th>
</tr>
<tr>
<th>2</th>
<th>Oracle</th>
<th>29.6 billion</th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>29.1 billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>16.8 billion</th>
</tr>
<tr>
<th>5</th>
<th>Symantec</th>
<th>5.6 billion</th>
</tr>
</table>
</body>
</html>
"""

class myHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('', 8000)
httpd = HTTPServer(server_address, myHandler)
print("My webserver is running...")
httpd.serve_forever()

## OUTPUT:
![alt text](<Screenshot 2025-04-09 134816.png>)

![alt text](<Screenshot 2025-04-09 134850.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
