
# MongoDB Integration in QE Python Worker Block

In the QE platform, each [Python Worker](https://qepal.com/docs/3-1-python) is automatically connected to the associated Service's MongoDB instance. You can access this database using `App.udb`, which is fully compatible with the `pymongo` library. This allows seamless document operations, such as insertion, retrieval, updating, and deletion, directly from within the Python Worker environment.

## Example 1: Insert Document into MongoDB

The following example demonstrates how to insert a document into the `test` collection and print the insertion result.

```python
import asyncio
from libs.bridge import NexusAPISpecs, App as AppClass, NexusMessageSpecs
from libs.bridge import setInterval, clearInterval, setTimeout

App = AppClass(public=True, rest=False)


# Insert a document into 'test' collection
collection = App.udb.get_collection("test")
result = collection.insert_one({"name": "armin", "age": 34, "score": 100})
print(result)


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
