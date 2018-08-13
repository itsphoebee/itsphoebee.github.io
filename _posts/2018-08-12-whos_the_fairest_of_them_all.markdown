---
layout: post
title:      "Who's the fairest of them all? "
date:       2018-08-13 02:55:49 +0000
permalink:  whos_the_fairest_of_them_all
---


In my ongoing journey to learn more about NodeJs/Express frameworks, I came across the use of many different databases. Graduating from Flatiron recently, I knew how to use SQLite with Rails. However, there are many other choices available depending on the type of data your application uses. So for this week we are going to discuss the most popular choices of databases used in web development.

However, before we start the list, it is important to discuss the difference between SQL and NoSQL databases.

Coming from a Rails backgroud, SQLite is an example of an SQL, or relational (RDBMS), database. Relational databases are table based and represent data in form of tables which consists of a certain number of rows of data. They have a predefined schema for structured data. It also uses SQL for defining, querying and manipulating data. NoSQL is the opposite; and stands for nonrelational or distributed database. This is because they are document oriented and often in key-value pairs (similar to JSON). NoSQL databases do not have a standard schema and instead have a dynamic one. Its queries are focused on collection of documents and is known as UnQL (Unstructured Query Language). 

Obviously, there are advantages and disadvantages of both. SQL databases are good for query intensive or complex query applications but NoSQL databases are great for data intensive applications (big data). In terms of scalability, SQL databases are vertically scalable and can manage increasing traffic by increasing the CPU or RAM of the server. NoSQL databases are horizontally scalable and can manage increasing traffic by adding more servers. SQL databases emphasize ACID properties (Atomicity, Consistency, Isolation and Durability) for protection and integrity at the tradeoff of a longer development and planning time. NoSQL allows different data types to be stored together and can result in quicker development time.

Popular SQL Databases include:

1. MySQL - a popular open-source database with large community input and has been around for a long time making it very stable 
2. MS-SQL Server - a user friendly database with stability, reliability and scalability and support from Microsoft
3. PostgreSQL - an open source object-relational database system, which means it incorporates object-oriented programming, allowing user-defined objects and table inheritance

Popular NoSQL Databases include:
1. MongoDB - a popular, open-source document based with a dynamic schema that allows for edits and improvements to new data without affecting the existing data
2. Redis - an open source database that is considered one of the fastest NoSQL server because it works with an in-memory dataset
3. CouchDB - also document based NoSQL database that allows access to database documents using your web browser
