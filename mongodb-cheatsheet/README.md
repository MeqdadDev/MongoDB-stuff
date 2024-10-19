# MongoDB Cheat Sheets


### Show all databases
```
show dbs
```

### Show Current database

```
db
```

### Select/Create Database

```
use RecordsDB
```

### Drop

```
db.dropDatabase()
```

### Create Collection

```
db.createCollection('RecordsDB')
```

### Show Collections

```
show collections
```

### Insert Document/Row (One at a time)

```
db.RecordsDB.insertOne({
    name: "Meqdad",
    career: "Back-end Developer",
    Tools: ["MongoDb", "Python", "GitHub"]
});
```

### Insert Multiple Documents/Rows

```
db.RecordsDB.insertMany([
    {name: "Ahmad",
    career: "Front-end Developer",
    Tools: ["HTML", "CSS", "JavaScript", "React"]},
    
    {name: "Yahya",
    career: "Mobile Developer",
    Tools: ["Flutter", "Swift", "Firebase"]}
    ])
```

### Get All Documents/Rows

```
db.RecordsDB.find()
```
Or
```
db.getCollection("RecordsDB").find()
```

### Find Documents/Rows

```
db.RecordsDB.find({name: "Yahya"})
```

### Sort Documents/Rows

```
# Descending
db.RecordsDB.find().sort({name: -1})

# Ascending
db.RecordsDB.find().sort({name: 1})
```

### Limit Documents/Rows

```
db.RecordsDB.find().limit(2)
```

### Count Documents/Rows

```
db.RecordsDB.find().count()
db.RecordsDB.find({name: "Yahya"}).count()
```

### Sort and Limit Documents/Rows

```
db.RecordsDB.find().limit(2).sort({name: 1})
```

### Find One Document/Row

```
db.RecordsDB.findOne({name: "Yahya"})
```

### Find Specific Fields

```
db.RecordsDB.find({name: "Ahmad"}, {
  name: 1,
  career: 1
})
```

### Foreach

```
db.RecordsDB.find().forEach(function(record) {
    print("Developer Name: " + record.name);
    print("-----------------------------");
})
```

### Update Specific Field

```
db.RecordsDB.updateOne({name: "Yahya"}, {$set:{career: "iOS Developer"}})
```

### Delete Document/Row

```
db.RecordsDB.deleteOne({name:"Ahmad"})
```
To delete many document/rows, use `deleteMany`.

### Rename Field

```
db.RecordsDB.update({name: "Ahmad"},
{
  $rename: {
    Tools: "Tech Stack"
  }
})
```

### Create an Index on the 'name' Field

```
db.RecordsDB.createIndex({name: 1})
```

### Get All Indexes in a Collection

```
db.RecordsDB.getIndexes()
```

### Query Execution Plan with Stats

```
db.RecordsDB.find({"name": "Yahya"}).explain("executionStats");
```

### Drop an Index

```
db.RecordsDB.dropIndex({name: 1})
```