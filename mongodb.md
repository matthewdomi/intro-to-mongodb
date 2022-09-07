# MongoDB Cheatsheet

show the version of database server
```
db.version()
```

Returns some statistics about MongoDB server
```
db.stats()
```

List all the database in the MongoDB server
```
show dbs
```

Switch to use the database specified
```
use <dbName>
```

Creates new collection in the database
```
db.createcollection("name")
```
List all collections under the specified database
```
show collections
```
##inserting document

Inserts one document into the collection
```
  insertOne({...})
  Syntax:
  db



