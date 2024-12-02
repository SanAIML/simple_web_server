# EX01 Developing a Simple Webserver

# Date: 16/09/2024
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
from django.shortcuts import render,HttpResponse
from http.server import HTTPServer,BaseHTTPRequestHandler



content='''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>System Specifications</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 20px;
            background-color: wheat;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        table {
            width: 100%;
            max-width: 600px;
            margin: 20px auto;
            border-collapse: collapse;
            background-color: #fff;
            
        }
        th, td {
            padding: 12px;
            
            border-bottom: 1px solid #ddd;
        }
        th {
            background-color:indianred;
            font-weight: bold;
            text-align: left;
        }
        td {
            color: black;
            text-align: center;
            background-color: lightcoral;
        }
        
    </style>
</head>
<body>

    <h1>System Specifications</h1>
    
    <table>
        <tr>
            <th>Device Name</th>
            <td>DESKTOP-MOHHBTU</td>
        </tr>
        <tr>
            <th>Processor</th>
            <td>13th Gen Intel(R) Core(TM) i5-1335U @ 1.30 GHz</td>
        </tr>
        <tr>
            <th>Installed RAM</th>
            <td>16.0 GB (15.7 GB usable)</td>
        </tr>
        <tr>
            <th>Device ID</th>
            <td>15EEA3B2-7EF5-4DEC-903D-577382C3C005</td>
        </tr>
        <tr>
            <th>Product ID</th>
            <td>00342-42709-07179-AAOEM</td>
        </tr>
        <tr>
            <th>System Type</th>
            <td>64-bit operating system, x64-based processor</td>
        </tr>
        <tr>
            <th>Pen and Touch</th>
            <td>No pen or touch input is available for this display</td>
        </tr>
    </table>
    
    

</body>
</html>
 '''


class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("this is my webserver")
server_address = ('',8012)
httpd=HTTPServer(server_address,Myserver)
httpd.serve_forever()
```
# OUTPUT:


![alt text](<Screenshot 2024-12-02 090629.png>)

![alt text](<Screenshot 2024-12-02 090827.png>)



# RESULT:
The program for implementing simple webserver is executed successfully.
