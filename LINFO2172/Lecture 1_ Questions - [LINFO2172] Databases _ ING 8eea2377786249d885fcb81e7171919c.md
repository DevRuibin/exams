# Lecture 1_ Questions - [LINFO2172] Databases _ INGInious

Class: LINFO2172
Created: May 27, 2023 11:17 PM
Reviewed: No
Type: Reading

### Information

| Author(s) | Siegfried Nijssen |
| --- | --- |
| Deadline | No deadline |
| Status | Succeeded |
| Grade | 100.0% |
| Grading weight | 1.0 |
| Attempts | 22 |
| Submission limit | No limitation |

### Submitting as

**Ruibin Zhang**

[Group management](https://inginious.info.ucl.ac.be/group/LINGI2172)

### For evaluation

Best submission

[06/03/2023 11:28:11 - 100.0%](https://inginious.info.ucl.ac.be/course/LINGI2172/lecture1_questions#)

**Question 1: What is the relationship between the terms "databases" and "database management systems"?**

They are synonyms

A database management system is a concrete implementation of a database. For instance, MySQL or SQL Server are database management systems; they are implementations of a database.

***A database is a collection of related information, which can be stored in a database management system***

A database is a concrete implementation of a database management system. For instance, MySQL or SQL Server are databases; they are implementations of a database management system.

> A database is a structured collection of data that is organized and stored for easy retrieval, manipulation and analysis. It can be thought of a repository that stores information in a structured format, typically in tables consisting of rows and columns. Database are designed to efficiently manage large amounts of data and provide mechanisms for querying and modifying data.
> 

> A DBMS is a software application or a set of software tools that enables the creation, maintenance, and utilization of databases. DBMS provides an interface between the users or applications and the underlying database, allowing users to interact with the data by defining, creating and manipulating databases. DBMS performs several essential functions, including data storage, data retrieval, data manipulation, data security, concurrency control, and transaction management. It provides mechanism for defining the structure of the database, specifying relationships between data elements, enforcing data integrity and optimizing the performance of data access and retrieval operatiors.
> 

**Question 2: Relational databases are databases that...**

contain entities and their relationships

consist of relations, where a "relation" can be thought of as a table with two columns

***consist of relations, where a "relation" can be thought of as a table***

> Relational databases are a type of database that organizes and stores data in the form of relations or tables. Each relation consists of rows and columns, where each row represents a record or an instance of an entity, and each column represents a specific attribute or characteristic of that entity. The relations or tables are related through common attributes, establishing relationships between the entities.
> 

**Question 3: Relational database management systems offer abstraction. What kind of abstraction?**

***Abstraction of the hardware: users don't need to see how and where data is stored on the hardware***

Abtraction of the schema of relations in the database: users don't always see the schema of relations in the database

***Abstraction of the relations in the full database: users don't always see the relations that are in the complete database***

<aside>
💡 1. Data Abstractions: This is where the complexity of data storage is abstracted away. Users of the database do not need to know how the data is stored in the physical storage media. They just have to understand the database in terms of a unified model, typically the relational model, which presents data in the form of tables.

</aside>

<aside>
💡 Logical Abstraction: The scheme of relations in the database is abstracted, meaning that the user doesn’t necessarily see the schema of the database. The database schema defines the logical structure of the database, including the tables and relationships. However, a user can access and manipulate the data without knowing the underlying schema. Database administrators typically manage this level of abstraction.

</aside>

<aside>
💡 Physical Abstraction: This involves abstracting the physical layout of the data. Databasers do not need to know where the data is physically stored and how it’s physically structured, whether it’s stored on an SSD, a spinning disk, or distributed across multiple physical locations.

</aside>

> Data abstraction concerns with hiding the overall complexities of data management, physical abstraction is specifically about abstracting away the details of the physical storage mechanisms.
> 

---

**Question 4: Relational database management systems excel at...**

Providing ease of use due to their built-in GUIs

***Providing ease of use due to a popular query language***

***Ensuring that data that is inserted in the database satisfies constraints determined by the database designer***

Storing large varieties in data, such as images, text, or graph structures

Providing quick response times in a distributed setting where many users are writing information into the database

<aside>
💡 1. Many DBMS tasks are performed via command line or scripts. RDBMS is not typically the best choice for highly unstructured data or complex graph structures. NoSQL databases might be better suited for such needs. RDBMS are best know for their ACID properties rather than their performance in high-write, distribute settings.

</aside>

**Question 5: We have a relation with the following schema: Student(Name,Class). Which of the following two expressions in Tutorial D would you expect to be more efficient, under the assumption that one can only evaluate a selection by traversing all tuples in a relation?**

***(Student WHERE Name="Lucas Martin") WHERE Class="Databases"***

(Student WHERE Class="Databases") WHERE Name="Lucas Martin"

<aside>
💡 The first one could be more efficient because it could potentially eliminate more tuples in the first traversal, leaving fewer tuples to be checked in the second traversal.

</aside>