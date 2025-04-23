# EX01 Developing a Simple Webserver

# Date:19/04/2025
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
```python
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>laptop configuration</title>
</head>
<style>
    body{
        background-color:aqua;
    }

    table{
        background-color:hotpink;
        border-collapse: collapse;
        box-shadow: 0;
        margin: 60px;
        text-align: center;
        color: black;
    }
    header{
        font-size: 420%;
        background-color: cornsilk;
    }

</style>
<body>
    <center>
        <header>
            MY LAPTOP CONFIGURATION
        </header>
    <table border="4px" width="600" height="400">
        <div class="heading">
        <tr style="font-size: x-large;">
            <th>S.NO</th>
            <th>COMPONENTS</th>
            <th>DETAILS</th>
        </tr>
        </div>
        <tr>
            <th>1</th>
            <th style="font-style: inherit;">PROCESSOR(CPU)</th>
            <td>13th Gen i5-1335U</td>
        </tr>
        <tr>
            <th>2</th>
            <th style="font-style: inherit;">MEMORY(RAM)</th>
            <td>16.0 GB</td>
        </tr>
        <tr>
            <th>3</th>
            <th style="font-style: inherit;">STORAGE</th>
            <td>512GB SSD</td>
        </tr>
        <tr>
            <th>4</th>
            <th style="font-style: inherit;">DISPLAY</th>
            <td>15.6-inch Full HD (1920x1080)</td>
        </tr>
        <tr>
            <th>5</th>
            <th style="font-style: inherit;">GRAPHICS(GPU)</th>
            <td>Integrated Intel UHD</td>
        </tr>
        <tr>
            <th>6</th>
            <th style="font-style: inherit;">BATTERY</th>
            <td>45 Wh, Up to 8 hours</td>
        </tr>
        <tr>
            <th>7</th>
            <th style="font-style: inherit;">OPERATING SYSTEM</th>
            <td>Windows 10 Home</td>
        </tr>

    </table>
    </center>
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
# OUTPUT:

![Screenshot 2025-04-23 105313](https://github.com/user-attachments/assets/488d611a-83b7-4d5a-8239-5253bfc38ffd)

![Screenshot 2025-04-23 105542](https://github.com/user-attachments/assets/a4c4af61-f2b5-4f3b-9c63-59a15cdad137)


# RESULT:
The program for implementing simple webserver is executed successfully.
