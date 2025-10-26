#### Universal Database on Javascript Blocks

Here is the document for using Universal database in all server-side JavaScript environments. This document is applicable to `Page backend`, `GAPI`, and `nodejs-worker`.

> It's fully compatible with the Node.js MongoDB driver.

> It's accessible with the `udb` global object.

---

### 📘 Example 1: Get Collections

```ts
  let collections = await udb.collections()
  console.log(collections)
```

### 📘 Example 2: Insert Document

```ts
  let t = udb.collection("test")
  let ack = await t.insertOne({name:"armin"})
  console.log(ack)
```

### 📘 Example 3: Query

```ts
  let t = udb.collection("test")
  let arr = await t.find({name:"armin"}).toArray()
  console.log(arr)
```

We can also use full MongoDB driver methods like `findOne`, `updateOne`, `updateMany`, `aggregation`, etc.