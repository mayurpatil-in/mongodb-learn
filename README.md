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

---

## 📂 3. Collection Commands

```bash
show collections                          # Show all collections
db.createCollection("<collection_name>")  # Create a collection
db.dropCollection("<collection_name>")    # Drop a collection
```

---

## 📝 4. Insert Documents

### Insert one document

```bash
db.collection.insertOne(
    {
 "maker": "Tata",
 "model": "Nexon",
 "fuel_type": "Petrol",
 "transmission": "Automatic",
 "engine": {
 "type": "Turbocharged",
 "cc": 1199,
 "torque": "170 Nm"
 },
 "features": [
 "Touchscreen",
 "Reverse Camera",
 "Bluetooth Connectivity"
 ],
 "sunroof": false,
 "airbags": 2
 }
)
```

---

### Insert multiple documents

```bash
db.collection.insertMany([
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

---

## 📖 5. Read Documents

```bash
db.collection.find()                       # Find all documents
db.collection.findOne()                    # Find one document
db.collection.find({ "name": "John Doe" }) # Find documents with specific field
 - db.cars.find({}, {"model":1})           # Find all documents with specific field
 - db.cars.find({}, {"model":1, "_id":0})  # 1 for include and 0 for exclude
 - db.cars.find({fuel_type: "Diesel"})
 - db.cars.find({features:"Sunroof"})

db.collection.find({ "age": { $gt: 25 } }) # Find documents with specific condition
```

---

## 📝 6. Update Documents

### Update one document

### ADD

```bash
db.cars.updateOne(
  {model: "Nexon"},
  {$set:{color: "Red"}}         # $set- Add new field
)

db.cars.updateOne(
  {model: "Nexon"},
  {$push:{features: "Heated seat"}} # $push- Add new element to array
)

db.cars.updateOne(
  {model: "Nexon"},
  {$push:{features: {$each: ["Wireless Charging", "Voice Control"]}}} # $push and $each- Add multiple element to array
)
```

### Remove

```bash
db.cars.updateOne(
  {model: "Nexon"},
  {$pull:{features: "Heated seat"}} # $pull- Remove element from array
)

db.cars.updateOne(
  {model: "Nexon"},
  {$unset:{color: 1}} # $unset- Remove field
)
```

### Update multiple documents

### Upsert

```bash
db.users.updateMany(
  {model: "Venue"},
  {$set:{maker: "Honda"}}
  { upsert: true }           # If document not found, it will create a new document
)
```

---
