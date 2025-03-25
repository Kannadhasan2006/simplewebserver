# EX01 Developing a Simple Webserver
## Date:1/03/2025

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
Developed by : Kannadhasan J   
Register number : 212224240071
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
    <title>Device Specifications</title>
    <style>
        body {
            font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
            margin: 20px;
        }
        table {
            width: 60%;
            border-collapse: collapse;
            margin: 20px auto;
            background: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }
        th, td {
            text-align: left;
            padding: 12px;
            border: 1px solid #ddd;p
        }
        th {
            background-color: #0078D7;
            color: white;
        }
        tr:nth-child(even) {
            background-color:aqua;
        }
        tr:hover {
            background-color:cornsilk;
        }
        caption {
            font-size: 20px;
            font-weight: bold;
            padding: 10px;
            text-align: center;
        }
    </style>
</head>
<body>
    <table>
        <caption>Device Specifications</caption>
        <tr>
            <th>Specification</th>
            <th>Details</th>
        </tr>
        <tr>
            <td>Device Name</td>
            <td>DESKTOP-MOHHBTU</td>
        </tr>
        <tr>
            <td>Processor</td>
            <td>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</td>
        </tr>
        <tr>
            <td>Installed RAM</td>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <td>Device ID</td>
            <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
        </tr>
        <tr>
            <td>Product ID</td>
            <td>00342-42708-86787-AAOEM</td>
        </tr>
        <tr>
            <td>System Type</td>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <td>Pen and Touch</td>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
</body>
</html>
"""


class MyHandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Request received")
        self.send_response(200)
        self.send_header('Content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())


server_address = ('', 8000)
httpd = HTTPServer(server_address, MyHandler)
print("My webserver is running...")
httpd.serve_forever()
```


## OUTPUT:
![Screenshot 2025-03-25 213121](https://github.com/user-attachments/assets/84bc1da9-3d6c-4f16-8178-73e07ac70eab)

![Screenshot 2025-03-25 213126](https://github.com/user-attachments/assets/5b811542-0421-4aa3-8407-82e53d14a280)


## RESULT:
The program for implementing simple webserver is executed successfully.
