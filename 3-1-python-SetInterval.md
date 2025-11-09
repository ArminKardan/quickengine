
# Periodic Task Execution in Python

In QE's Python, periodic task execution is handled using `SetInterval` instead of standard Python techniques. This ensures better compatibility and safety with the asynchronous system design of QE workers.

---

## Example:
In this example we fire a SetInterval function by setInterval decorator named "c" and after 5 counts it stopped using clearInterval.

```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)

json = App.find(app="emyapp")

counter = 0
@setInterval(500, "c")
def f():
    global counter
    counter += 1
    print("hi", counter)
    if counter > 5:
        clearInterval("c")

loop = asyncio.get_event_loop()
loop.run_forever()

```

Interval utilities make it easy to perform regular background tasks in a robust, thread-safe manner tailored to the QE ecosystem.
