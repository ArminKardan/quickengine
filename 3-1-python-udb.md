
# MongoDB Integration in QE `python-worker`

In the QE platform, each `python-worker` is automatically connected to the associated `explore`'s MongoDB instance. You can access this database using `App.udb`, which is fully compatible with the `pymongo` library. This allows seamless document operations, such as insertion, retrieval, updating, and deletion, directly from within the `python-worker` environment.

## Example 1: Insert Document into MongoDB

The following example demonstrates how to insert a document into the `test` collection and print the insertion result.

```python
from libs.startup import startup
startup()
import asyncio
from libs.bridge import APISpecs, App as app

App = app(resource="python", public=True, rest=False)

async def api(specs: APISpecs):
    if specs.cmd == "ping":
        return {"pong": True}

# Insert a document into 'test' collection
collection = App.udb.get_collection("test")
result = collection.insert_one({"name": "armin", "age": 34, "score": 100})
print(result)

App.xmpp.onapi = api
loop = asyncio.get_event_loop()
loop.run_forever()
```

## Example 2: Retrieve All Documents

This example shows how to retrieve all documents from the `test` collection and print them as a list.

```python
collection = App.udb.get_collection("test")
result = collection.find({}).to_list()
print(result)
```

---

By using `App.udb` and the standard `pymongo` syntax, developers can leverage powerful MongoDB functionality directly in their QE `python-worker` blocks.
