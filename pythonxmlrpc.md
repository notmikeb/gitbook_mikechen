
### robotremoteserver
python module
https://pypi.python.org/pypi/robotremoteserver

A xmlrpc server for remote testing

### XML-RPC Request Format
Use HTTP standard protocol
https://www.tutorialspoint.com/xml-rpc/xml_rpc_request.htm

```

POST /xmlrpc HTTP 1.0
User-Agent: myXMLRPCClient/1.0
Host: 192.168.124.2
Content-Type: text/xml
Content-Length: 169
<?xml version="1.0"?>
<methodCall>
   <methodName>circleArea</methodName>
      <params>
         <param>
            <value><double>2.41</double></value>
         </param>
      </params>
</methodCall>
```

### Real usage case

Smartsniff
monitor the socket traffic on windows
http://www.nirsoft.net/utils/smsniff.html
![](/assets/smsniff.gif)

*client

python -m robotremoteserver test http://127.0.0.1:8088

*server

python server.py

```
from robotremoteserver import RobotRemoteServer
from examplelibrary import ExampleLibrary

server = RobotRemoteServer(ExampleLibrary(), host='localhost', port=8088)
server.serve()
```

### robotframework xmlrpc
Request
```
POST /RPC2 HTTP/1.1
Host: 127.0.0.1:8088
Accept-Encoding: gzip
User-Agent: xmlrpclib.py/1.0.1 (by www.pythonware.com)
Content-Type: text/xml
Content-Length: 111

<?xml version='1.0'?>
<methodCall>
<methodName>get_keyword_names</methodName>
<params>
</params>
</methodCall>
```

Response
```
HTTP/1.0 200 OK
Server: BaseHTTP/0.3 Python/2.7
Date: Fri, 23 Jun 2017 11:58:18 GMT
Content-type: text/xml
Content-length: 302

<?xml version='1.0'?>
<methodResponse>
<params>
<param>
<value><array><data>
<value><string>count_items_in_directory</string></value>
<value><string>strings_should_be_equal</string></value>
<value><string>stop_remote_server</string></value>
</data></array></value>
</param>
</params>
</methodResponse>
```
