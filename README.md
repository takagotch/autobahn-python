### autobahn-python
---
https://github.com/crossbario/autobahn-python

```
```

```py
from autobahn.twisted.websocket import WebServerProtocol

class MyServerProtocol(WebSocketServerProtocol):

  def onConnect(self, request):
    print()
  
  def onOpen():
    print()
    
  def onMessage():
    if isBinary:
      print()
    else:
      print()
      
    self.sendMessage(payload, isBinary)
    
  def onClose(self, wasClean, code, reason):
    print("WebSocket connection closed: {}".format(reason))


```

```
```


