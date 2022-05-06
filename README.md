1. In the last tutorial we learned how to leverage the Scrapy framework to solve common web scraping problems. Today we are going to take a look at Selenium (with Python ❤️ ) in a step-by-step tutorial.

Selenium refers to a number of different open-source projects used for browser automation. It supports bindings for all major programming languages, including our favorite language: Python.

The Selenium API uses the WebDriver protocol to control a web browser, like Chrome, Firefox or Safari. The browser can run either localy or remotely.

At the beginning of the project (almost 20 years ago!) it was mostly used for cross-browser, end-to-end testing (acceptance tests).

Now it is still used for testing, but it is also used as a general browser automation platform. And of course, it us used for web scraping!

Selenium is useful when you have to perform an action on a website such as:

Clicking on buttons

Filling forms

Scrolling

Taking a screenshot

It is also useful for executing Javascript code. Let's say that you want to scrape a Single Page Application. Plus you haven't found an easy way to directly call the underlying APIs. In this case, Selenium might be what you need.

2. Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis.

Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page). Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet or loaded into a database. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else. An example would be to find and copy names and telephone numbers, or companies and their URLs, or e-mail addresses to a list (contact scraping).

Web scraping is used for contact scraping, and as a component of applications used for web indexing, web mining and data mining, online price change monitoring and price comparison, product review scraping (to watch the competition), gathering real estate listings, weather data monitoring, website change detection, research, tracking online presence and reputation, web mashup, and web data integration.

Web pages are built using text-based mark-up languages (HTML and XHTML), and frequently contain a wealth of useful data in text form. However, most web pages are designed for human end-users and not for ease of automated use. As a result, specialized tools and software have been developed to facilitate the scraping of web pages.

Newer forms of web scraping involve monitoring data feeds from web servers. For example, JSON is commonly used as a transport storage mechanism between the client and the web server.

There are methods that some websites use to prevent web scraping, such as detecting and disallowing bots from crawling (viewing) their pages. In response, there are web scraping systems that rely on using techniques in DOM parsing, computer vision and natural language processing to simulate human browsing to enable gathering web page content for offline parsing.

3. Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.

Indexes are special data structures [1] that store a small portion of the collection's data set in an easy to traverse form. The index stores the value of a specific field or set of fields, ordered by the value of the field. The ordering of the index entries supports efficient equality matches and range-based query operations. In addition, MongoDB can return sorted results by using the ordering in the index.

The following diagram illustrates a query that selects and orders the matching documents using an index:

Fundamentally, indexes in MongoDB are similar to indexes in other database systems. MongoDB defines indexes at the collection level and supports indexes on any field or sub-field of the documents in a MongoDB collection.

Default _id Index

MongoDB creates a unique index on the _id field during the creation of a collection. The _id index prevents clients from inserting two documents with the same value for the _id field. You cannot drop this index on the _id field.

NOTE

In sharded clusters, if you do not use the _id field as the shard key, then your application must ensure the uniqueness of the values in the _id field to prevent errors. This is most-often done by using a standard auto-generated ObjectId.

Create an Index

➤ Use the Select your language drop-down menu in the upper-right to set the language of the examples on this page.

To create an index in the Mongo Shell, use db.collection.createIndex().

db.collection.createIndex( <key and index type specification>, <options> )

MongoDB Shell

The following example creates a single key descending index on the name field:

db.collection.createIndex( { name: -1 } )

MongoDB Shell

The db.collection.createIndex() method only creates an index if an index of the same specification does not already exist.

[1]

MongoDB indexes use a B-tree data structure.

Index Names

The default name for an index is the concatenation of the indexed keys and each key's direction in the index ( i.e. 1 or -1) using underscores as a separator. For example, an index created on { item : 1, quantity: -1 } has the name item_1_quantity_-1.

You can create indexes with a custom name, such as one that is more human-readable than the default. For example, consider an application that frequently queries the products collection to populate data on existing inventory. The following createIndex() method creates an index on item and quantity named query for inventory:

db.products.createIndex(

{ item: 1, quantity: -1 } ,

{ name: "query for inventory" }

)

You can view index names using the db.collection.getIndexes() method. You cannot rename an index once created. Instead, you must drop and re-create the index with a new name.

Index Types

MongoDB provides a number of different index types to support specific types of data and queries.

Single Field

In addition to the MongoDB-defined _id index, MongoDB supports the creation of user-defined ascending/descending indexes on a single field of a document.

4. Set expressions are used to define the scope of a calculation. The central part of the set expression is the set modifier that specifies a selection. This is used to modify the user selection, or the selection in the set identifier, and the result defines a new scope for the calculation.

5. db.collection.aggregate([

    { $project : { "Tags._id" : 1 }},

    { $unwind : "$Tags" },

    { $match: {$or: [{"Tags._id":"tag1"},{"Tags._id":"tag2"}]}},

    { $group: { 

        _id : "$_id",

        count: { $sum:1 } 

    }},

    {$sort: {"count":-1}}

  ],

  {

    explain:true

  }1.Cassandra: Cassandra is a high-performance and highly scalable distributed NoSQL database management system. Cassandra deals with unstructured data and handles a high volume of incoming data velocity. In Cassandra data is written in many locations also data come from many locations this row represents a unit of replication and the column represents a unit of storage. 

RDBMS: Relational Database Management System (RDBMS) is a Database management system or software that is designed for relational databases and uses Structured Query Language (SQL) for querying and maintaining the database. It deals with structured data and handles moderate incoming data velocity. In RDBMS mainly data is written in one location also data come from one/few locations and a row represents a single record column that represents an attribute. 

Difference between Cassandra and RDBMS:

S.No.

CASSANDRA

RDBMS

1.

Cassandra is a high performance and highly scalable distributed NoSQL database management system.

RDBMS is a Database management system or software which is designed for relational databases.

2.

Cassandra is a NoSQL database.

RDBMS uses SQL for querying and maintaining the database.

3.

It deals with unstructured data.

It deals with structured data.

4.

It has a flexible schema.

It has fixed schema.

5.

Cassandra has peer-to-peer architecture with no single point of failure.

RDBMS has master-slave core architecture means a single point of failure.

6.

Cassandra handles high volume incoming data velocity.

RDBMS handles moderate incoming data velocity.

7.

In RDBMS there is limited data source means data come from many locations.

In Cassandra there are various data source means data come from one/few location.

8.

It supports simple transactions.

It supports complex and nested transactions.

9.

In Cassandra the outermost container is Keyspace.

In RDBMS the outermost container is database.

10.

Cassandra follows decentralized deployments.

RDBMS follows centralized deployments.

11.

In Cassandra data written in many locations.

In RDBMS mainly data are written in one location.

12.

In Cassandra row represents a unit of replication.

In RDBMS row represents a single record.

13.

In Cassandra column represents a unit of storage.

In RDBMS column represents an attribute.

14.

In Cassandra, relationships are represented using collections.

In RDBMS relationships are represented using keys and join etc.

         2.           This chapter introduces the Cassandra query language shell and explains how to use its commands.

By default, Cassandra provides a prompt Cassandra query language shell (cqlsh) that allows users to communicate with it. Using this shell, you can execute Cassandra Query Language (CQL).

Using cqlsh, you can

define a schema,

insert data, and

execute a query.

3. Cassandra is based on distributed system architecture. In its simplest form, Cassandra can be installed on a single machine or in a docker container, and it works well for basic testing. A single Cassandra instance is called a node. Cassandra supports horizontal scalability achieved by adding more than one node as a part of a Cassandra cluster. The scalability works with linear performance improvement if the resources are configured optimally.

4. 

📖 A Student Hub

For high school and college students alike, this Notion template is intended for those seeking a rubric to keep track of class grades. Included in this template is also a template for daily to-dos and unique class notebooks. The example used is for an American college freshman.

5. Python is an object-oriented programming language. Everything is in Python treated as an object, including variable, function, list, tuple, dictionary, set, etc. Every object belongs to its class. For example - An integer variable belongs to integer class. An object is a real-life entity. An object is the collection of various data and functions that operate on those data. An object contains the following properties.

State - The attributes of an object represents its state. It also reflects the properties of an object.

Behavior - The method of an object represents its behavior.

Identity - Each object must be uniquely identified and allow interacting with the other objects.

Let's understand the object in the aspect of classes.

The classes and objects are the essential key to the object-oriented programming. Classes are the blueprint of the object. Classes are used to bundling the data and functionality together. Each newly created class must have its object. Let's understand real-life example of class and object.

A human is a class which may have may attributes such as walking, sleeping, thinking, etc. Suppose we want to name and age of 100 humans, so we don't need to create a class for every person. We just need to instantiate the multiple objects of that perticular class.
  1. In the last tutorial we learned how to leverage the Scrapy framework to solve common web scraping problems. Today we are going to take a look at Selenium (with Python ❤️ ) in a step-by-step tutorial.

Selenium refers to a number of different open-source projects used for browser automation. It supports bindings for all major programming languages, including our favorite language: Python.

The Selenium API uses the WebDriver protocol to control a web browser, like Chrome, Firefox or Safari. The browser can run either localy or remotely.

At the beginning of the project (almost 20 years ago!) it was mostly used for cross-browser, end-to-end testing (acceptance tests).

Now it is still used for testing, but it is also used as a general browser automation platform. And of course, it us used for web scraping!

Selenium is useful when you have to perform an action on a website such as:

Clicking on buttons

Filling forms

Scrolling

Taking a screenshot

It is also useful for executing Javascript code. Let's say that you want to scrape a Single Page Application. Plus you haven't found an easy way to directly call the underlying APIs. In this case, Selenium might be what you need.

2. Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet, for later retrieval or analysis.

Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page). Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet or loaded into a database. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else. An example would be to find and copy names and telephone numbers, or companies and their URLs, or e-mail addresses to a list (contact scraping).

Web scraping is used for contact scraping, and as a component of applications used for web indexing, web mining and data mining, online price change monitoring and price comparison, product review scraping (to watch the competition), gathering real estate listings, weather data monitoring, website change detection, research, tracking online presence and reputation, web mashup, and web data integration.

Web pages are built using text-based mark-up languages (HTML and XHTML), and frequently contain a wealth of useful data in text form. However, most web pages are designed for human end-users and not for ease of automated use. As a result, specialized tools and software have been developed to facilitate the scraping of web pages.

Newer forms of web scraping involve monitoring data feeds from web servers. For example, JSON is commonly used as a transport storage mechanism between the client and the web server.

There are methods that some websites use to prevent web scraping, such as detecting and disallowing bots from crawling (viewing) their pages. In response, there are web scraping systems that rely on using techniques in DOM parsing, computer vision and natural language processing to simulate human browsing to enable gathering web page content for offline parsing.

3. Indexes support the efficient execution of queries in MongoDB. Without indexes, MongoDB must perform a collection scan, i.e. scan every document in a collection, to select those documents that match the query statement. If an appropriate index exists for a query, MongoDB can use the index to limit the number of documents it must inspect.

Indexes are special data structures [1] that store a small portion of the collection's data set in an easy to traverse form. The index stores the value of a specific field or set of fields, ordered by the value of the field. The ordering of the index entries supports efficient equality matches and range-based query operations. In addition, MongoDB can return sorted results by using the ordering in the index.

The following diagram illustrates a query that selects and orders the matching documents using an index:

Fundamentally, indexes in MongoDB are similar to indexes in other database systems. MongoDB defines indexes at the collection level and supports indexes on any field or sub-field of the documents in a MongoDB collection.

Default _id Index

MongoDB creates a unique index on the _id field during the creation of a collection. The _id index prevents clients from inserting two documents with the same value for the _id field. You cannot drop this index on the _id field.

NOTE

In sharded clusters, if you do not use the _id field as the shard key, then your application must ensure the uniqueness of the values in the _id field to prevent errors. This is most-often done by using a standard auto-generated ObjectId.

Create an Index

➤ Use the Select your language drop-down menu in the upper-right to set the language of the examples on this page.

To create an index in the Mongo Shell, use db.collection.createIndex().

db.collection.createIndex( <key and index type specification>, <options> )

MongoDB Shell

The following example creates a single key descending index on the name field:

db.collection.createIndex( { name: -1 } )

MongoDB Shell

The db.collection.createIndex() method only creates an index if an index of the same specification does not already exist.

[1]

MongoDB indexes use a B-tree data structure.

Index Names

The default name for an index is the concatenation of the indexed keys and each key's direction in the index ( i.e. 1 or -1) using underscores as a separator. For example, an index created on { item : 1, quantity: -1 } has the name item_1_quantity_-1.

You can create indexes with a custom name, such as one that is more human-readable than the default. For example, consider an application that frequently queries the products collection to populate data on existing inventory. The following createIndex() method creates an index on item and quantity named query for inventory:

db.products.createIndex(

{ item: 1, quantity: -1 } ,

{ name: "query for inventory" }

)

You can view index names using the db.collection.getIndexes() method. You cannot rename an index once created. Instead, you must drop and re-create the index with a new name.

Index Types

MongoDB provides a number of different index types to support specific types of data and queries.

Single Field

In addition to the MongoDB-defined _id index, MongoDB supports the creation of user-defined ascending/descending indexes on a single field of a document.

4. Set expressions are used to define the scope of a calculation. The central part of the set expression is the set modifier that specifies a selection. This is used to modify the user selection, or the selection in the set identifier, and the result defines a new scope for the calculation.

5. db.collection.aggregate([

    { $project : { "Tags._id" : 1 }},

    { $unwind : "$Tags" },

    { $match: {$or: [{"Tags._id":"tag1"},{"Tags._id":"tag2"}]}},

    { $group: { 

        _id : "$_id",

        count: { $sum:1 } 

    }},

    {$sort: {"count":-1}}

  ],

  {

    explain:true

  }
  
