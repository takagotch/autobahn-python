### autobahn-python
---
https://github.com/crossbario/autobahn-python

```
```

```py
from autobahn.twisted.websocket import WebServerProtocol

class MyServerProtocol(WebSocketServerProtocol):

  def onConnect(self, request):
    print("Client connecting: {}".format(request.peer))
  
  def onOpen(self):
    print("WebSocket connection open.")
    
  def onMessage(self, payload, isBinary):
    if isBinary:
      print("Binary message received: {} bytes".format(len(payload)))
    else:
      print("Text message received: {}".format(payload.decode('utf8')))
      
    self.sendMessage(payload, isBinary)
    
  def onClose(self, wasClean, code, reason):
    print("WebSocket connection closed: {}".format(reason))

from autobahn.twisted.wamp import ApplicationSession

class MyComponent(ApplicationSession):

  @inlineCallbacks
  def onJoin(self, details):
    
    def onevent(msg):
      print("Got event: {}".format(msg))
      
    yield self.subscribe(onevent, 'com.myapp.hello')
    
    self.publish('com.myapp.hello', 'Hello, world!')
    
    def ad2(x, y):
      return x + y
      
    self.register(add2, 'com.myapp.add2')
    
    res = yeild self.call('com.myapp.add2', 2, 3)
    print("Got result: {}".format(res))
    
```

```
```


