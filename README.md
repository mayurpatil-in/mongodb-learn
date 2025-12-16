# 📦 MongoDB Commands – Complete Guide

A complete collection of **MongoDB shell (mongosh) commands** for beginners to advanced users.

---

## 🚀 1. MongoDB Shell Basics

```bash
mongosh
exit
cls        # Windows
clear      # Linux / macOS
```

---

## 🚀 2. Database Commands

```bash
show dbs            # Show all databases
use <db_name>       # Use a database
db                  # Show current database
db.dropDatabase()   # Drop current database
```

## 📂 3. Collection Commands

```bash
show collections                          # Show all collections
db.createCollection("<collection_name>")  # Create a collection
db.dropCollection("<collection_name>")    # Drop a collection
```

## 📝 4. Insert Documents

```bash
db.collection.insertOne({                # Insert one document
    "name": "John Doe",
    "age": 30,
    "email": "john.doe@example.com"
})
```

```bash
db.collection.insertMany([               # Insert multiple documents
    {
        "name": "John Doe",
        "age": 30,
        "email": "john.doe@example.com"
    },
    {
        "name": "Jane Doe",
        "age": 25,
        "email": "jane.doe@example.com"
    }
])
```

## 📖 5. Read Documents

```bash
db.collection.find()                       # Find all documents
db.collection.findOne()                    # Find one document
db.collection.find({ "name": "John Doe" }) # Find documents with specific field
db.collection.find({ "age": { $gt: 25 } }) # Find documents with specific condition
```
