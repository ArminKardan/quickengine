# Send Nexus API request to a built-in QE app from Python worker:
Here we send an api ping request to `eagents` from front-end of a Python Worker block.


```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

res = await App.api(app="eagents", cmd="ping")
print(res)

loop = asyncio.get_event_loop()
loop.run_forever()
```

# Send Nexus API request + Data to a built-in QE app from Python worker:

```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

res = await App.api(app="eagents", cmd="ping", body={"myval":"Hi from Python!"})
print(res)

loop = asyncio.get_event_loop()
loop.run_forever()
```

> Note that body can only be `list` or a `dictionary` no any other types are supported.