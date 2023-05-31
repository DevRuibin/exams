# Lecture 6_ Questions - [LINFO2172] Databases _ INGInious

Class: LINFO2172
Created: May 28, 2023 9:43 AM
Reviewed: No
Type: Reading

### Information

| Deadline | No deadline |
| --- | --- |
| Status | Succeeded |
| Grade | 100% |
| Grading weight | 1.0 |
| Attempts | 5 |
| Submission limit | No limitation |

### Submitting as

**Ruibin Zhang**

[Group management](https://inginious.info.ucl.ac.be/group/LINGI2172)

### For evaluation

Best submission

[28/05/2023 09:39:26 - 100.0%](https://inginious.info.ucl.ac.be/course/LINGI2172/lecture9_questions#)

### Submission history

- 28/05/2023 09:39:26 - 100.0%
- 28/05/2023 09:39:21 - 80.0%
- 28/05/2023 09:39:16 - 80.0%
- 28/05/2023 09:39:05 - 80.0%
- 28/05/2023 09:37:28 - 80.0%

---

Please answer to all the questions. Internal error {} has not a valid extension. {} is too heavy.

**Question 1: We are storing a table with schema R(id,name,address), where id is the primary key of the table. The table has 100.000 records, each record takes 100 bytes, and is not allowed to span multiple blocks. The block size of the disk is 1024 bytes. We store the data ordered on the id attibute, and do not have an additional index on the table. How many blocks do we need to load from disk in the worst case to load the record with identifier 10?**

10.000

16

13

17

***14***

<aside>
💡 In the worst case, we would need to perform a binary search on the entire table to find the record with identifier 10.  ⇒ $log_{2}{100,000} = 14.xxxx$

</aside>

**Question 2: We are storing a table with schema R(id,name,address), where id is the primary key of the table. The table has 100.000 records, each record takes 100 bytes, and is not allowed to span multiple blocks. The block size of the disk is 1024 bytes. We store the data ordered on the id attibute, and do not have an additional index on the table. How many blocks do we need to load from disk in the worst case to load the record with name Siegfried Nijssen?**

10.000

17

14

13

16

**Question 3: Indexes in SQLite**

✓

×Close

While the id is not explicitly included in the index, note that in SQLite an index stores the rowid, which in this case corresponds to the id attribute.

While the id is not explicitly included in the index, note that in SQLite an index stores the rowid, which in this case corresponds to the id attribute.

Consider the following table together with an additional index:

```
CREATE TABLE Patient (
  id INTEGER PRIMARY KEY,
  birthday TEXT,
  birthplace TEXT
);

CREATE INDEX Patient_Birthplace ON Patient ( birthplace, birthday );
```

For which queries will SQLite calculate the answer completely from the Patient_Birthplace index?

SELECT id FROM Patient WHERE birthday = "2018-02-01";

SELECT birthday, id FROM Patient WHERE birthplace = "Louvain-la-Neuve";

SELECT id FROM Patient WHERE birthplace = "Louvain-la-Neuve" AND birthday >= "2018-02-01";

SELECT birthplace FROM Patient WHERE id = 1;

SELECT birthday FROM Patient WHERE birthplace = "Louvain-la-Neuve";

**Question 4: Number of indexes used in SQLite**

Consider the following table:

```
CREATE TABLE Patient (
  location TEXT,
  id INTEGER,
  name TEXT,
  PRIMARY KEY(location,id)
);
```

Furthermore, consider the following query:

```
SELECT id FROM Patient WHERE location = "Bruxelles";
```

How many indexes will be accessed by SQLite to answer this query?

3

1

0

2

**Question 5: Number of indexes used in SQLite**

Consider the same data as in the earlier question. How many indexes will be accessed by SQLite for this query?

```
SELECT name FROM Patient WHERE location = "Bruxelles";
```

1

0

3

2

Submit

**Share my result on:**×

Running INGInious v.0.8.6
© 2014-2023 Université catholique de Louvain.[INGInious is distributed under AGPL license](http://www.inginious.org/)

×