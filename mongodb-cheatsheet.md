# MongoDB Theory Cheatsheet

A concise guide to MongoDB concepts for theory exams. Focuses on core ideas, architecture, and practical understanding.

---

## Table of Contents
- [What is MongoDB?](#what-is-mongodb)
- [NoSQL vs SQL](#nosql-vs-sql)
- [Core Concepts](#core-concepts)
- [CRUD Operations](#crud-operations)
- [Schema Design](#schema-design)
- [Indexes](#indexes)
- [Aggregation](#aggregation)
- [Relationships](#relationships)
- [Mongoose (ODM)](#mongoose-odm)
- [Sample Code Snippets](#sample-code-snippets)

---

## What is MongoDB?
- MongoDB is a NoSQL, document-oriented database.
- Stores data as JSON-like documents (BSON format).
- Schema-less: Documents in a collection can have different structures.
- Designed for scalability, flexibility, and high performance.

## NoSQL vs SQL
- **SQL (Relational):** Structured tables, fixed schema, joins, ACID transactions.
- **NoSQL (MongoDB):** Collections of documents, flexible schema, denormalized data, BASE consistency.

| Feature         | SQL (Relational) | NoSQL (MongoDB)      |
|-----------------|------------------|----------------------|
| Data Structure  | Tables/Rows      | Collections/Documents|
| Schema          | Fixed            | Flexible             |
| Joins           | Yes              | No (embed/reference) |
| Transactions    | ACID             | BASE                 |
| Scaling         | Vertical         | Horizontal           |

## Core Concepts
- **Database:** Container for collections.
- **Collection:** Group of related documents (like a table).
- **Document:** JSON-like object (key-value pairs).
- **Field:** Key-value pair in a document.
- **_id:** Unique identifier for each document.

## CRUD Operations
- **Create:** `insertOne()`, `insertMany()`
- **Read:** `find()`, `findOne()`
- **Update:** `updateOne()`, `updateMany()`, `replaceOne()`
- **Delete:** `deleteOne()`, `deleteMany()`

**Example:**
```js
// Insert
users.insertOne({ name: 'Alice', age: 25 });

// Find
users.find({ age: { $gte: 18 } });

// Update
users.updateOne({ name: 'Alice' }, { $set: { age: 26 } });

// Delete
users.deleteOne({ name: 'Alice' });
```

## Schema Design
- **Embedded Documents:** Store related data inside a single document (denormalization).
- **References:** Store ObjectId of related document (normalization).
- **Choose embedding for:** One-to-few, data that is always accessed together.
- **Choose referencing for:** One-to-many, large or frequently changing related data.

**Example:**
```js
// Embedded
{
  _id: 1,
  name: 'Alice',
  address: { city: 'NY', zip: '10001' }
}

// Reference
{
  _id: 1,
  name: 'Alice',
  addressId: ObjectId('...')
}
```

## Indexes
- Improve query performance.
- Default index on `_id`.
- Create additional indexes for frequently queried fields.
- Types: single field, compound, text, geospatial, unique.

**Example:**
```js
users.createIndex({ email: 1 }, { unique: true });
```

## Aggregation
- Used for advanced data processing (grouping, filtering, transforming).
- Aggregation pipeline: sequence of stages (`$match`, `$group`, `$sort`, `$project`, etc.).

**Example:**
```js
users.aggregate([
  { $match: { age: { $gte: 18 } } },
  { $group: { _id: '$city', count: { $sum: 1 } } },
  { $sort: { count: -1 } }
]);
```

## Relationships
- **One-to-One:** Embed or reference.
- **One-to-Many:** Embed array or reference.
- **Many-to-Many:** Reference array of ObjectIds.

**Example:**
```js
// One-to-many reference
{
  _id: 1,
  name: 'Alice',
  posts: [ObjectId('...'), ObjectId('...')]
}
```

## Mongoose (ODM)
- Mongoose is an Object Data Modeling (ODM) library for MongoDB in Node.js.
- Defines schemas, models, and provides validation, middleware, and query helpers.

**Example:**
```js
const mongoose = require('mongoose');
const userSchema = new mongoose.Schema({
  name: String,
  email: { type: String, unique: true },
  age: Number
});
const User = mongoose.model('User', userSchema);

// Create
const user = new User({ name: 'Alice', email: 'alice@example.com' });
await user.save();

// Find
const users = await User.find({ age: { $gte: 18 } });
```

---

This cheatsheet covers the most important MongoDB theory for exams. Focus on understanding documents, collections, CRUD, schema design, and aggregation! 