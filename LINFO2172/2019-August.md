Class: LINFO2172
Created: May 29, 2023 4:18 PM
Reviewed: No

# **August 2019**

## **Part 1**

### **1**

The SQL query  is looking to find the names (pname) of 
persons from the Person table who are parents (pid = C.parent_id) 
but do not have a male child.

Answer: 

B

see ![1.jpg](2019-August/1.jpg)

### **2**

I need to evaluate the count function.
see [evaluating.sql](evaluating.sql)

> The test database's person's relation can be found [relation.jpg](2019-August/relation.jpg)

Answer:

![2.jpg](2019-August/2.jpg)

### **3**

```sql
select child_id as p1, parent_id as p2
from ChildOf
union
select child_id as p1, parent_id as p2
from childOf,
     childOf as C
where parent_id = C.child_id;
```

### **4**

![4.jpg](2019-August/4.jpg)

### **5**

It returns pairs of parent's name and child's name that the child's gender is female.

### **6**

One can always perform an algorithm that consists of the following steps:

1. Cascading selection
2. Commuting selection and pushing selection
3. Pushing projection
4. Introducing joins

To obtain an equivalent algorithm that is more efficient.

1. Cascading selection
   $$
   \pi_{pname}(S) \\
   T \leftarrow Person \times Event \times Location
   S \leftarrow \sigma_{pid=person\_id} (\sigma_{location\_id=lid}(\sigma_{country='Belgium'}(\sigma_{pid=100}(T))))
   $$


2. Computing selection and pushing selection
   $$
   \pi_{pname}(S) \\
   PE \leftarrow \sigma_{pid=person\_id}(\sigma_{pid=100}(Person)) \times Event\\
   T \leftarrow \sigma_{location\_id=lid}(\sigma_{country='Belgium'}(Location) \times PE) \\
   S \leftarrow T\\
   $$


3. Pushing Projection
   $$
   \pi_{pname}(S) \\
   P \leftarrow \pi_{pid, pname} (\sigma_{pid=100}(Person))\\
   E \leftarrow \pi_{location_id, person_id} Event\\
   PE \leftarrow \pi_{location_id, pname} ( \sigma_{pid=person\_id}(P \times E))\\
   L \leftarrow \pi_{lid} (\sigma_{country="Belgium"}(Location)\\
   T \leftarrow \sigma_{lid=location\_id} (L \times PE)\\
   S \leftarrow T\\
   $$

4. Introducing joins
   $$
   \pi_{pname}(S) \\
   P \leftarrow \pi_{pid, pname} (\sigma_{pid=100}(Person))\\
   E \leftarrow \pi_{location_id, person_id} Event\\
   PE \leftarrow \pi_{location_id, pname} (P \Join_{pid=person_id} E)\\
   L \leftarrow \pi_{lid} (\sigma_{country="Belgium"}(Location)\\
   T \leftarrow  (L \Join_{lid=location_id} PE)\\
   S \leftarrow T\\
   $$
   
