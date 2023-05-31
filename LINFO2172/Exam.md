# Exam

Class: LINFO2172
Created: May 29, 2023 4:18 PM
Reviewed: No

# **June 2019**

## **Part 1**

**Explanation** of the database schema:

The owner of the car and the person who rented the car belong to the customer.


### **1**

```
SELECT CR.day_id, C.type, COUNT(DISTINCT CR.car_id)
FROM CarRent CR, Car C
WHERE CR.car_id = C.car_id
AND NOT EXISTS (
 SELECT *
 FROM Car C2
 WHERE C2.owner_id = C.cust_id
)
GROUP BY CR.day_id, C.type; # I assume the day means day_id
```

`CarRent` and `Car`: -> `car_id`, `cust_id`, `day_id`, `owener_id`, `type`.

group by: count the number of each type's car in each day rented.

<aside>
💡 For the fist question of exam in June 2019, the SQL query statement is not correct.

</aside>

<aside>
💡 There is no field `cust_id` in relation `Car`

</aside>

<aside>
💡 There is no field `day` in relation `CarRent`

</aside>

### **2**

```sql
select C1.City as City1, C2.City as City2, COUNT(DISTINCT CR.day)
from Customer C1,
     Customer C2,
     CarRent CR,
     Car C
where CR.cust_id = C1.cid
  AND CR.car_id = C.car_id
  AND C.owner_id = C2.cid.
```

**Explanation**:


`CR.cust_id = C1.cid`: get the customer's information

`CR.car_id = C.car_id AND C.owner_id = C2.cid.`: get the owner's information

so we can refactor the query:

```sql
select tenant.City as City1, owner.City as City2, COUNT(DISTINCT CR.day)
from Customer tenant,
     Customer owner,
     CarRent CR,
     Car C
where CR.cust_id = tenant.cid
  AND CR.car_id = C.car_id
  AND C.owner_id = owner.cid.
```

**Answer**: 

![answer3](exam/2.jpg)


### **3**

```sql
select distinct cust_id as cid
from CarRent
intersect
select owner_id as cid
from Car c, CarRent cr
where c.car_id = cr.car_id
```

### **4**

![answer4](exam/3.jpg)


### **5**

This query will return the owner's id who owns at least two cars.

### **6**

The relational algebra is used to query the types of cars that have been rented by customers who come from
"LLN".


![answer6](exam/6.png)

### **7**

1. For car reservation relation, we need to use index on `day_id` and `cust_id` to speed up the query.
2. For customer relation, we need to use index on `cid` and `city` to speed up the query.

The indexes are enough to speed up the query, but it may not be necessary to create
indexes on `cust_id` in the car reservation relation if the number of car reservations is smaller than the number of customers.

DBMS can locate the tuples where day_id >= 50 by using index `day_id`.
DBMS can locate the tuples where city = "Bastogne" by using index city.

Then DBMS can join the two tables by using the index `cid` or `cust_id`.
The choice depends on the size of the two tables.