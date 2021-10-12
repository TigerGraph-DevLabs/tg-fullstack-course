---
template: overrides/main.html
---

# Middleware

**Step I. Connect to your TigerGraph Cloud Solution: <br>**
Perfect! Now we’re ready to integrate pyTigerGraph into our API. Open `main.py` in your editor of choice and import pyTigerGraph.

```
import pyTigerGraph as tg
```

Next, create a connection to your TigerGraph Cloud server.

```
conn = tg.TigerGraphConnection(host=Credential.HOST, username=Credential.USERNAME, password=Credential.PASSWORD, graphname=Credential.GRAPHNAME)
conn.apiToken = conn.getToken(conn.createSecret())
```
