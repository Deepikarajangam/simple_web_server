# EX01 Developing a Simple Webserver

# Date:30-11-2024
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
views.py
from django.shortcuts import render,HttpResponse
from http.server import HTTPServer,BaseHTTPRequestHandler

# def trial(request):
#     return HttpResponse('<h1>Hello</h1>')
# def slot(request):
#     return render(request,'home.html')
content ='''
<!DOCTYPE html>
<html>

<head>
    <center>
    <title>Device Specifications</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            height: 100%;
            font-family: Arial, sans-serif;
            background-color: aqua;
        }

        .content {
            height: 462px;
            width: 726px;
            padding: 80px;
    
            display: flex;
            
            background-size: cover;
            text-align: center;
        }

        h1 {
            font-size: 30px;
            font-weight: bold;
            font-style: italic; 
            
            color: darkblue;
        }

       table {
        
            border-collapse: collapse;
            border size:5px;
            height:230px;
            width: 500px;
            margin-right: 0px;
            margin-left:100px ;
            
            background-color:reen;
        }

         th,
         td {
            padding: 0px;
            border: 2px solid black;
            font-size:50 px;
            color:block;
        }

        td {
            text-align: left;
        }
    </style>
    </center>
</head>

<body>
    <center>
        <h1>Device Specifications </h1>
    <div class="content">
        
        
        <table>
            <tr>
                <td>Device Name</td>
                <td>DESKTOP</td>
            </tr>   
            <tr>
                <td>Processor</td>
                <td>13th Gen Intel(R) Core(TM) i3-1305U 1.60 GHz</td>
            </tr>
            <tr>
                <td>Installed RAM</td>
                <td>8.00 GB (7.69 GB usable)</td>
            </tr>
            <tr>
                <td>Device ID</td>
                <td>2DB9535D-8827-43C0-A0AA-3DD3241218DA</td>
            </tr>
            <tr>
                <td>Product ID</td>
                <td>00356-24769-58908-AAOEM</td>
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
    </div>
    </center>
</body>

</html> 
'''


  
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver")
serveraddress =('',8000)
httpd = HTTPServer(serveraddress,MyServer)
httpd.serve_forever()

   


# OUTPUT:![image](https://github.com/user-attachments/assets/9ab8b098-26b5-463a-ae67-771106b32a14)

# RESULT:
The program for implementing simple webserver is executed successfully.
