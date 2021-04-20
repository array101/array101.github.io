+++
title = "Getting started with MongoDB for postgreSQL devs"
slug = "mongodb-basics-for-relational-db-devs"
layout = "page.html"
date = 2017-12-20
draft = false
[taxonomies]
tags = ["database", "nosql"]
+++

If you primarily work with postgreSQL (or any relational database systems) and have heard a lot of buzz regarding NoSQL databases and want to get started in one of those, here's a breif intro to get started on 'mongoDB' with one-one comparision with postgreSQL. It's one of the widely used NoSQL database (especially if you work with RESTful APIs).

There's a number of different classification of NoSQL databases: document-based, key-value based, etc.

**mongoDB** is a document based NoSQL database.

## **Creating a new DB**

Creating a new database is just plain one command into the mongo shell.
Type `mongo` on your terminal/bash shell to enter the mongo shell and use this one liner to create a new DB.

```zsh
mongo_shell> use blogDb;
# --
template1=#> CREATE DATABASE blogDb;
```

## **Dropping a DB**

Dropping an existing database from mongo shell is another one liner.

```zsh
mongo_shell> db.dropDatabase()
# --
template1=#> DROP DATABASE blogDb;
```

## **Creating a new collection**

'collections' can be analouged with what we have 'tables' in traditional relational databases.

```zsh
mongo_shell> db.createCollection('posts')
# --
template1=#> CREATE TABLE posts (title VARCHAR(20), tag VARCHAR(20), permalink VARCHAR(20), content TEXT);
```

## Dropping a collection

Dropping a 'collections' is just chaining `drop()` command on the name of the collection of the DB currently in use.

```zsh
mongo_shell> db.posts.drop()
# --
template1=#> DROP TABLE posts;
```

## **CRUD operations**
---

- **CREATE document**
```zsh
mongo_shell> db.posts.insert({ title: 'hello world', tag: 'dbms', permalink: 'db-mongo', content: 'start something with hello world!' })
# --
template1=#> INSERT INTO posts (title, tag, permalink, content) VALUES ('hello world', 'dbms', 'db-mongo', 'start something with hello world!');
```

- **READ document/s**


READ all documents from a collection
```zsh
mongo_shell> db.posts.find()
# --
template1=#> SELECT * FROM posts;
```

READ a single document from a collection
```zsh
mongo_shell> db.posts.find({ permalink: 'db-mongo' })
# --
template1=#> SELECT * FROM posts WHERE permalink='db-mongo';
```

- **UPDATE document/s**

UPDATE a single document

```zsh
mongo_shell> db.posts.update({"permalink": "db-mongo"}, {$set : {"title": "hello mongoDB", "tag": "database"}})
# --
template1=#> UPDATE posts SET title='hello mongoDB', tag='database' WHERE permalink='db-mongo';
```

Bulk UPDATE multiple documents

```zsh
mongo_shell> db.posts.update({}, { $set : { "tag": "nosql"}}, { multi: true })
# --
template1=#> UPDATE posts SET tag='nosql';
```

- **DELETE document/s**

DELETE a single document

```zsh
mongo_shell> db.posts.remove({ "permalink": "db-mongo" })
# --
template1=#> DELETE FROM posts WHERE permalink='db-mongo';
```

Bulk DELETE multiple documents
```zsh
mongo_shell> db.posts.remove({})
# --
template1=#> DELETE FROM posts;
```

## **Miscellaneous**
---

- **Exporting/Dumping DB data**

Export - dump BSON formatted DB data into dump directory at current directory

```zsh
mongo_shell> mongodump --db blogDb
```

- **Export - dump JSON formatted DB data of a collection to a file as JSON array**

```zsh
mongo_shell> mongoexport --db blogDb --collection posts --out data/posts.json --jsonArray --pretty
```

- **Export - spit out JSON formatted DB data of a collection into terminal shell**

```zsh
mongo_shell> mongoexport --db blogDb --collection posts
```

- **Importing data to a DB**

Import - BSON exported, gzip compressed data to a new DB

```zsh
mongo_shell> mongorestore --db db_to_create --gzip /path/of/dump
```

- **Import - JSON file into a DB collection**

```zsh
mongo_shell> mongoimport --db blogDb --collection posts --jsonArray posts.json
```