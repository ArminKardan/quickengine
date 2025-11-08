#### User Database on Javascript Blocks

Here is the document for using **User database** in `GAPI` and `Page backend` only on `XWebsite` block.

> It's fully compatible with the Node.js MongoDB driver.

> It's accessible with the `xdb` global object only on `XWebsite` server side.

---

### 📘 Example 1: Get Collections

```ts
  let collections = await xdb.collections()
  console.log(collections)
```

### 📘 Example 2: Insert Document

```ts
  let t = xdb.collection("test")
  let ack = await t.insertOne({name:"armin"})
  console.log(ack)
```

### 📘 Example 3: Query

```ts
  let t = xdb.collection("test")
  let arr = await t.find({name:"armin"}).toArray()
  console.log(arr)
```

We can also use full MongoDB driver methods like `findOne`, `updateOne`, `updateMany`, `aggregation`, etc.