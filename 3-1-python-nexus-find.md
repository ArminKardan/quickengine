# Find Nexus Workers

In the example below we find all workers that is available from a Service named `emyapp` and send a `ping` by [Nexus API](https://qepal.com/docs/3-1-python-nexus-api-send.md) to it.


```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

json = App.find(app="emyapp")

if json["code"] == 0 and len(json["jids"]) > 0:
    json_api = App.api(app="emyapp", cmd="ping", jid=json["jids"][0])
    print(json_api)

loop = asyncio.get_event_loop()
loop.run_forever()
```
