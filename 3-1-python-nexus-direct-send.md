# Send Data using Nexus Direct request to a sample app:
Here we send an api ping request to `emyapp` from a Python Worker block.


```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

App.direct(app="emyapp", body={"myval":"Hi from Python!"} )

loop = asyncio.get_event_loop()
loop.run_forever()
```

> Note that body can only be `list` or a `dictionary` no any other types are supported.