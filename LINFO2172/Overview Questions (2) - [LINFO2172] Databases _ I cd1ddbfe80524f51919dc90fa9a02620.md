# Overview Questions (2) - [LINFO2172] Databases _ INGInious

Class: LINFO2172
Created: May 28, 2023 11:33 AM
Reviewed: No
Type: Reading

### Information

| Author(s)        | Siegfried Nijssen |
|------------------|-------------------|
| Deadline         | No deadline       |
| Status           | Succeeded         |
| Grade            | 100%              |
| Grading weight   | 0.0               |
| Attempts         | 11                |
| Submission limit | No limitation     |

**Question 1: A database developer wishes to store a large number of images in a NoSQL database. For a given key, the database should be able to recover the associated image. Which NoSQL database is the most appropriate; it does not provide more functionality than necessary?**

Apache HBase

MongoDB

***Amazon DynamoDB***

**Question 2: Differences between MongoDB and Apache HBase are...**

***Apache HBase allows to partition the columns over multiple servers; MongoDB does not allow such partitioning***

Apache HBase allows to retrieve a given item more efficiently

***MongoDB provides a more advanced querying interface than Apache HBase***

Apache HBase allows to partition the rows over multiple servers; MongoDB does not allow such partitioning

***Apache HBase allows to retrieve all values for a given attribute more efficiently***

**Question 3: The CAP theorem is an important basis for NoSQL databases. What do the letters stand for?**

Concurrency, Atomicity, Partition tolerance

Concurrency, Availability, Partition tolerance

Consistency, Atomicity, Partition tolerance

***Consistency, Availability, Partition tolerance***

**Question 4: A relational database needs to maintain the ACID properties. Ensuring ACID can however degrade the performance of a distributed relational database in comparison with a document store such as MongoDB. Which are valid arguments for this degradation in performance in comparison with MongoDB?**

***A read operation for a given record needs to wait until a write lock for that record has been released.***

A read operation for a given record requires more time as the system needs to find out where the record is stored.

A write operation that spans multiple servers requires more network traffic.

***A write operation that spans multiple servers can only commit if all servers confirm the operation.***

**Question 5: Consider the query below. Which database system does this query access?**

db.inventory.find( { status: "A", name: "Mark" } )

Neo4J

SQLite

Apache Hive

***MongoDB***

**Question 6: What is "sharding" in a distributed relational database?**

Two different relations are stored on two different servers.

***The records in the same relation are distributed over multiple servers if the relation is too large.***

The data in the same relation are copied over multiple servers to ensure redundancy.

The attributes in the same relation are distributed over multiple servers if the relation is too large.

**Question 7: A NoSQL database that remains available even if a part of the database stops working...**

has a soft state

***is basically available***

is eventually consistent

**Question 8: Your employer asks you to build a data warehouse. The warehouse needs to be able to answer complex SQL queries, or SQL-like queries, on a given database very efficiently. Which system do you pick?**

Apache HDFS

Apache Hadoop

***Apache Hive***

Apache HBase

**Question 9: Which statements are correct for a wide-column store?**

***A wide-column store requires that every record has the same set of column families***

***A wide-column store can store two different records on a different server***

A wide-column store requires that every record has the same set of columns

A wide-column store always stores each column on a different server

**Question 10: What are correct interpretations of the word "partitioning" in the literature of NoSQL databases?**

***Splitting data over multiple servers***

Splitting queries in multiple expressions of relational algebra

***Splitting a network in multiple independent components (usually as a result of connection that stops working)***

Splitting transactions in multiple read/write operations

Submit

**Share my result on:**×

Running INGInious v.0.8.6
© 2014-2023 Université catholique de Louvain.[INGInious is distributed under AGPL license](http://www.inginious.org/)

×