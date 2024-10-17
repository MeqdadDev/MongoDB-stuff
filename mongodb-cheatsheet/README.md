# MongoDB Cheat Sheets


### Show all databases
```
show dbs
```

## Show Current database

```
db
```

## Select/Create Database

```
use RecordsDB
```

## Drop

```
db.dropDatabase()
```

## Create Collection

```
db.createCollection('RecordsDB')
```

## Show Collections

```
show collections
```

## Insert Document/Row (One at a time)

```
db.RecordsDB.insertOne({
    name: "Meqdad",
    career: "Back-end Developer",
    Tools: ["MongoDb", "Python", "GitHub"]
});
```

## Insert Multiple Documents/Rows

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

## Get All Documents/Rows

```
db.RecordsDB.find()
```
Or
```
db.getCollection("RecordsDB").find()
```
