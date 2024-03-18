# EX01 Developing a Simple Webserver
## Date:08.03.2024

## AIM:
To develop a simple webserver to serve html pages.

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
<html>
<head>
<h1 align="center">SOFTWARE COMPANIES<h1>
<title>
TOP SOFTWARE COMPANIES WITH HIGH REVENUES
</title>
</head>
<body bgcolor="cyan">
<table border="3" align="center">
<caption>TOP FIVE REVENUE GENERATING SOFTWARE COMPANIES</caption>
  <tr>
    <td>SNO</td>
    <td>Companies</td>
    <td>Revenue</td>
  </tr>
  <tr>
    <td>1.</td>
    <td>APPLE</td>
    <td>$385.70 B</td>
  </tr>
<tr>
    <td>2.</td>
    <td>Alphabet (Google)</td>
    <td>$307.39 B</td>
  </tr>
<tr>
    <td>3.</td>
    <td>Microsoft</td>
    <td>$227.58 B</td>
  </tr>
<tr>
    <td>4.</td>
    <td>IBM</td>
    <td>$61.85 B</td>
  </tr>
<tr>
    <td>5.</td>
    <td>Oracle</td>
    <td>$51.62 B </td>
  </tr>
</table>

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
![Screenshot (242)-1](https://github.com/Hemaprasad-N/simplewebserver/assets/135933397/8a2cbf0d-8385-4c9c-b6f5-a76da6ab75aa)
![Screenshot (243)](https://github.com/Hemaprasad-N/simplewebserver/assets/135933397/cbe2740f-8edc-4a0e-96c0-b72642e7f5c8)


## RESULT:
The program for implementing simple webserver is executed successfully.
