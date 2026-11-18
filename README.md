# EX01 Developing a Simple Webserver

# Date:11/11/2026
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:

```
from http.server import HTTPServer,BaseHTTPRequestHandler
content='''<!DOCTYPE html>
<html>
<head>
    <title>My Laptop Info</title>
</head>
<body>

    <h1 align="center">My Laptop Info</h1>

    <table border="1" cellpadding="10" cellspacing="0" align="center">
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Model Name</td>
            <td>TravelLite TL15-53M-G2</td>
        </tr>
        <tr>
            <td>OS</td>
            <td>Windows 11 Home SL + Ubuntu</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>Intel Core 5 Processor 210H</td>
        </tr>
        <tr>
            <td>Display</td>
            <td>15.6" Antiglare FHD IPS Display</td>
        </tr>
        <tr>
            <td>Webcam</td>
            <td>FHD Webcam</td>
        </tr>
        <tr>
            <td>Memory</td>
            <td>16 GB DDR5 Memory</td>
        </tr>
        <tr>
            <td>Storage</td>
            <td>SSD 512GB</td>
        </tr>
        <tr>
            <td>Battery</td>
            <td>3 Cell 55.2Wh Li-ion Polymer Battery</td>
        </tr>
    </table>

</body>
</html>'''
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get Request Recived...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
server_address=("",8000)
httpd=HTTPServer(server_address,MyServer)
httpd.serve_forever()
```

# OUTPUT:
![alt text](<../web ex1.png>)
![alt text](../table-web.png)


# RESULT:
The program for implementing simple webserver is executed successfully.
