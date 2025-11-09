# Delayed Task Execution in Python

## Example

This is the Python equivalent of JavaScript's `setTimeout` using `SetTimeout` in a Python Worker block.

```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

json = App.find(app="emyapp")

@setTimeout(5000)
def f():
    print("timedout")

loop = asyncio.get_event_loop()
loop.run_forever()
```
