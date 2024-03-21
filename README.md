# EX01 Developing a Simple Webserver
## Date:12/03/24

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


```py
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
</head>
<body>
<table border="5">
<tr>
<th>Rank</th>
<th>Company</th>
<th>Revenue</th>
<th>FY</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft</td>
<td>$86.8</td>
<td>2014</td>
</tr>
<tr>
<td>2</td>
<td>Oracle</td>
<td>$37.1</td>
<td>2013</td>
</tr>
<tr>
<td>3</td>
<td>SAP</td>
<td>$20.9</td>
<td>2013</td>
</tr>
<tr>
<td>4</td>
<td>Symantec</td>
<td>$6.8</td>
<td>2013</td>
</tr>
<tr>
<td>5</td>
<td>VMware</td>
<td>$5.2</td>
<td>2013</td>
</tr>
<tr>
<td>6</td>
<td>CA Technologies</td>
<td>$4.7</td>
<td>2013</td>
</tr>
<tr>
<td>7</td>
<td>Adobe Systems</td>
<td>$4.4</td>
<td>2013</td>
</tr>
<tr>
<td>8</td>
<td>Fiserv</td>
<td>$4.5</td>
<td>2013</td>
</tr>
<tr>
<td>9</td>
<td>Intuit</td>
<td>$4.2</td>
<td>2013</td>
</tr>
<tr>
<td>10</td>
<td>Amadeus IT Group</td>
<td>$3.8</td>
<td>2013</td>
</tr>
</table>
</body>
</html>
"""
class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8080)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```


## OUTPUT:
![Screenshot 2024-03-21 223117](https://github.com/DHOESH123/simplewebserver/assets/150319589/c9080fc5-09e5-4411-b606-264906677f32)




## RESULT:
The program for implementing simple webserver is executed successfully.
