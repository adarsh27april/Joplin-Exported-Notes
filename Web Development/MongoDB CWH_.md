
- [Tut 80](#tut-80)
- [Tut 81](#tut-81)
- [Insering Data in mongo DB](#insering-data-in-mongo-db)
- [Tut 82](#tut-82)
- [Querying a Database- Searching for data in MongoDB](#querying-a-database--searching-for-data-in-mongodb)
  - [Contents of DB- this is the result *without using any filter* :](#contents-of-db--this-is-the-result-without-using-any-filter-)
  - [By using a correct filter & an incorrect filter :](#by-using-a-correctfilter-an-incorrect-filter-)
  - [`gte`](#gte)
  - [`gt`](#gt)
  - [And Operator( `,` )](#and-operator--)
  - [`lt`](#lt)
  - [`lte`](#lte)
  - [`or`](#or)
  - [Projection parameter](#projection-parameter)
- [Tut 83](#tut-83)
- [Deleting Data from MongoDB](#deleting-data-from-mongodb)
- [Tut 84](#tut-84)
  - [Updating data from Mongo DB](#updating-data-from-mongo-db)
- [Tut 85](#tut-85)
  - [85 MongoDB Compass Mongoose](#85-mongodb-compass-mongoose)
  - [86](#86)

* * * 
* * * 

# Tut 80


![01dc0a5c446229751827ab92ff33a7fc.png](../_resources/01dc0a5c446229751827ab92ff33a7fc.png)

- RDBMS, More Scalable
- Document oriented DataBase stores the data in the form of documents

![efcf4d9547404acd75b219e661784d1a.png](../_resources/efcf4d9547404acd75b219e661784d1a.png)

> For 3rd point: 
> - lhs <=> RDBMS like MYSQL    &   
> - rhs <=> MongoDB
> - in comparision to MS EXCEL:

&larr; &rarr; &uarr; &darr;

Comparision between MongoDB and MS EXCEL
| MongoDB  | MS EXCEL |
| -------- | -------- |
| Database | Workbook |
| Tables   | Sheet    |
| Rows     | Rows     |

**BSON**: Simiar to JSON except the fact that here we have to declare the type of the data type (integer, char, etc.)



![0acfab90f6ec57564b1b7740b106e24f.png](../_resources/0acfab90f6ec57564b1b7740b106e24f.png)

![17579081385e6a3926faab4a434d7e22.png](../_resources/17579081385e6a3926faab4a434d7e22.png)

> **`mongod`**    =    *mongo demon* is the name of the process for running MongoDB, on running the process the DB will start mongo is a cmd shell for connecting to mongod, by using mongo we can also connect to mongod running on a different machine, instead of mongo we can also use python, nodejs for connecting to mongod

To start `mongo` first run `mongod` in a different terminal

> When there is no db created then it uses the default db: **`text`**

> `show dbs` command shows db which contain atleast 1 row

> On using command `use adarsh` : 
> - ***if*** :  db with name `adarsh` is already present then it uses that
> ![3390e9e480cf853a313637e8ad3fd8c4.png](../_resources/3390e9e480cf853a313637e8ad3fd8c4.png)
> - ***else*** : it creates a new db named `adarsh`
> ![53824f713872f9b7557d7866e02a8c7f.png](../_resources/53824f713872f9b7557d7866e02a8c7f.png)

![77ab51afb729ac6fd41889e2cc137209.png](../_resources/77ab51afb729ac6fd41889e2cc137209.png)


* * * 
* * * 

# Tut 81

# Insering Data in mongo DB

`use harryKart` consider harryKart as a fictional e-comm website*

> **`insertOne()`** :
> 
> `db.items.insertOne({name: "Samsung 30s", price: 22000, rating: 4.5, qty: 233, sold: 98})`
> 
> ![2eb67a2f2ff91385db1a17488f86522d.png](../_resources/2eb67a2f2ff91385db1a17488f86522d.png)

*ये जो हमने बनाए है उसे **collection** कहा जाता है MongoDB मे, we can refer it as a table in RDBMS or a object in JS.*


> **`insertMany()`**
> 
> `db.items.insertMany([{name: "Samsung 30s", price: 22000, rating: 4.5, qty: 233, sold: 98}, {name: "Moto 30s", price: 29000, rating: 3.5, qty: 133, sold: 598}, {name: "Moto 30s", price: 129000, rating: 2.5, qty: 633, sold: 58, isBig: true}])`
> 
> ![0202187bf525cc1d9018f81d39ef8a45.png](../_resources/0202187bf525cc1d9018f81d39ef8a45.png)

*to get all items in present in the DB*
**`db.items.find()`**

- अगर हम `mongod` और `mongo` दोनों को बंद कर के फिर से start करे तो हमे अपना पुराना samsung वाला DB दिखेगा--जरूर दिखेगा

- जो हमने mongod process चलाई है वो commands को ले-ले कर _data directory_ मे data को store कर देगा, & since the data is stored there it'll persist there until we delete the data

Mongo gives unique id to all the elements that are added in the DB, so the Samsung 30s is added twice(dupicates) in the DB with ***different ids***

Primary(1°) key in MongoDB is `ObjectId` assigned by MongoDB itself

MongoDB doesn't enforce a schema on the tables (*like in SQL we have to insert data in same column, format, ...*), it's more like JS Objects, as seen in the following ex: 

`db.items.insertMany([{name: "Samsung 30s", price: 22000, rating: 4.5, qty: 233, sold: 98}, {name: "Moto 30s", price: 29000, rating: 3.5, qty: 133, sold: 598}, {name: "Moto 30s", price: 129000, rating: 2.5, qty: 633, sold: 58, isBig: true}])`

![8c2630d3ac76c024d584e3d033a6247b.png](../_resources/8c2630d3ac76c024d584e3d033a6247b.png)


* * * 
* * * 

# Tut 82

# Querying a Database- Searching for data in MongoDB

## Contents of DB- this is the result *without using any filter* : 
`db.items.find()` :
![42c9e85adc1b5f941e1e3abbe2e2e927.png](../_resources/42c9e85adc1b5f941e1e3abbe2e2e927.png)


## By using a correct filter & an incorrect filter :

- `db.items.find({"price": 3.5})`
- `db.items.find({"rating": 3.5})` - will return all objects with rating = 3.5

![977d8d7668cc5b466a9719b6153ae738.png](../_resources/977d8d7668cc5b466a9719b6153ae738.png)

On applying correct filter we get 2 documents.


**Some Complex Filters**

## `gte`

`db.items.find({rating: {$gte: 3.5}})`

`gte` = *greater than equal to*

![f5cbc2f785766a208cee9d4b7a5adef3.png](../_resources/f5cbc2f785766a208cee9d4b7a5adef3.png)


## `gt`

`db.items.find({rating: {$gt: 3.5}})`

`gt` = *greater than*

![90378b46547127de1c467a7948e5817f.png](../_resources/90378b46547127de1c467a7948e5817f.png)


## And Operator( `,` )

`db.items.find({rating: {$gt: 3.5}, price: {$gt: 4000}})`

![a70235465d1bba2dba51cd0d5141f0c5.png](../_resources/a70235465d1bba2dba51cd0d5141f0c5.png)

## `lt` 

`db.items.find({rating: {$lt: 3.5}, price: {$gt: 114000}})`
![a65739207e022803d3c2a93c56f88d2b.png](../_resources/a65739207e022803d3c2a93c56f88d2b.png)


## `lte`

less than equal to


## `or`


`db.items.find({ $or: [ {rating: {$gt: 3.5}}, {"price": {$gt: 114000}} ] })`

![f18394ba98cff1f212b89e6859cd4402.png](../_resources/f18394ba98cff1f212b89e6859cd4402.png)

## Projection parameter

`db.items.find({rating: {$gt: 3.5}}, {rating: 1}) `
- rating: 1 means that only rating will be shown, others like: price, name, qty won't be shown.

![f8b83e9efc5e9be153c97f3c42888331.png](../_resources/f8b83e9efc5e9be153c97f3c42888331.png)


`db.items.find({rating: {$gt: 3.5}}, {rating: 1, qty: 1})`
- rating: 1, qty: 1 means that only rating and qty will be shown, others like: price, name, qty won't be shown.

![59f0d11a8b1144356517b362ba470f49.png](../_resources/59f0d11a8b1144356517b362ba470f49.png)


* * * 
* * * 

# Tut 83

# Deleting Data from MongoDB

Has syntax similar to searching

- `show dbs`
- `use adarsh`
- `show collections`

- `db.items.find()`
![4a4cb9bde405246a93240193972b41b7.png](../_resources/4a4cb9bde405246a93240193972b41b7.png)

- `db.items.find({price: 22000})`
![d9d7594f65de79804a96242a2043691b.png](../_resources/d9d7594f65de79804a96242a2043691b.png)

Deleting Items from the MongoDB Database:

`db.items.deleteOne({price: 22000})`
- If Multiple *documents*(elements/object) exist for the command then it deletes the very first enry.
- will delete first entry in case of multi document match

![2f4c679141b725a291ae55a957c3023a.png](../_resources/2f4c679141b725a291ae55a957c3023a.png)

deleteMany deletes all the matching entries

![8fa071443cb19f877cb6d91d42ec129c.png](../_resources/8fa071443cb19f877cb6d91d42ec129c.png)



* * * 
* * * 

# Tut 84

## Updating data from Mongo DB

CRUD- Create Read Update & Delete - expected from any DB

- `show dbs` : shows all the databases
- `use adarsh` :  adarsh database को use करने के लिए
- `show collections` : collections in Mongo = Tables in RDBMS
- To create New Database : `use new_DB_Name` 
- `db.anotherCollection.insertOne({a : 123})`

![5c9fd86be87da9971ec9ffec6f392e5a.png](../_resources/5c9fd86be87da9971ec9ffec6f392e5a.png)

![b818269e97abd2205742b0226a904f1c.png](../_resources/b818269e97abd2205742b0226a904f1c.png)

`db.items.updateOne({filterObject}, {vlaueToBeChanged})`
`db.items.updateOne({name: "Moto 30s"}, {$price:2})`

> - on running command: `db.items.updateOne({name: "Moto 30s"}, {$set: {price:2}})`
> ![2a11a8455802d9a00be2680742f491e8.png](../_resources/2a11a8455802d9a00be2680742f491e8.png)

> - `db.items.updateMany({name: "Moto 30s"}, {$set: {price : 3, rating : 1}})`
> 
> ![88e803ae682c1752cc59826e3a47d38b.png](../_resources/88e803ae682c1752cc59826e3a47d38b.png)

!!!CRUD operations complete here!!!


* * * 
* * * 

# Tut 85

## 85 MongoDB Compass Mongoose

- run `mongod` on *powershell admin* and Open MongoDB Compass
- MongoDB Compass connects to process `mongod`

Mongoose
- Mongoose is used by NodeJS for connecting to `mongod`
- Mongoose is an Object Data Modeling(ODM) Library for MongoDB and Node.js
- It's just a layer b/w Node.JS and MongoDB

![ce3a0fb3222804fe3357d1337ecaa7e1.png](../_resources/ce3a0fb3222804fe3357d1337ecaa7e1.png)

[Mongoose Getting Started](https://mongoosejs.com/docs/)

```javascript
const mongoose = require('mongoose');
mongoose.connect('mongodb://localhost/adarsh', {useNewUrlParser: true, useUnifiedTopology: true});

const db = mongoose.connection;
db.on('error', console.error.bind(console, 'connection error:'));
db.once('open', function() {
  // 
  console.log("We're connected to MongoDB");
});
```
Output: 
![97822333db031abfe1ad6edfe74b92c0.png](../_resources/97822333db031abfe1ad6edfe74b92c0.png)


## 86
