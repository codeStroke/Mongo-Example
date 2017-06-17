# MongoDB by Example

> Collection of `MongoDB tips and tricks`, want to add your tips? Checkout [contributing.md](./contributing.md)

P.S: All these commands are tested on `MongoDB shell version v3.4.2`.
## MongoDB Package Component
* [Import data into the collection using JSON generated By Mongoexport](#import-data-into-the-collection-using-json-generated-by-mongoexport)
* [Import data into the collection using regular JSON](#import-data-into-the-collection-using-regular-json)

## Mongo Shell
   * [Show list of Databases](#show-list-of-databases)
   * [Copy Database](#copy-database)
   * [Copy Database Using Host and user credential](#copy-database-using-host-and-user-credential)

## MongoDB CRUD Operations
   > each document stored in a collection requires a unique _id field that acts as a primary key. 
   If an inserted document omits the _id field, the MongoDB driver automatically generates an ObjectId for the _id field.
   * [Insert a single document](#insert-a-single-document)
   * [Insert multiple documents](#insert-multiple-documents)
   
   
<!--------------------- MongoDB Package Component --------------------------->
### Import data into the collection using JSON generated By Mongoexport
```sh
mongoimport --db <databaseName> --collection <collectionName> --drop --file <jsonFile>.json
```
### Import data into the collection using regular JSON
```sh
mongoimport --db <databaseName> --collection <collectionName> --drop --file <jsonFile>.json --jsonArray
```
<!----------- Mongo Shell----------------------------------------------------->
### Show list of Databases
```bash
show dbs
```
### Copy Database
```sh
db.copyDatabase(fromdb, todb)
```
### Copy Database Using Host and user credential
```
db.copyDatabase(fromdb, todb, fromhost, username, password, mechanism)
```
<!--------------------- MongoDB CRUD Operations --------------------------->

### Insert a single document

```bash
db.mycollection.insertOne(
   { bookName: "Indian History", price: 100, tags: ["History"], size: { h: 28, w: 35.5, uom: "cm" } }
  )
```

### Insert multiple documents

```bash
db.mycollection.insertMany([
   { bookName: "Modern science", price: 500.34, tags: ["science"], size: { h: 28, w: 35.5, uom: "cm" } },
   { bookName: "Computer Design", price: 300, tags: ["computer"], size: { h: 28, w: 35.5, uom: "cm" } },
  )]
```
### Update a field to an empty array in all documents
```
db.collectionName.update({}, {$set :{fieldName:[]}}, {multi:true})
```