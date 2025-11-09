# Service MongoDB Database

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