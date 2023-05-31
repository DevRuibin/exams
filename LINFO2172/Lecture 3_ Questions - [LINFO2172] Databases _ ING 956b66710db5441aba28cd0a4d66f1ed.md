# Lecture 3_ Questions - [LINFO2172] Databases _ INGInious

Class: LINFO2172
Created: May 28, 2023 10:31 AM
Reviewed: No
Type: Reading

### Information

| Deadline | No deadline |
| --- | --- |
| Status | Succeeded |
| Grade | 100% |
| Grading weight | 1.0 |
| Attempts | 23 |
| Submission limit | No limitation |

### Submitting as

**Ruibin Zhang**

[Group management](https://inginious.info.ucl.ac.be/group/LINGI2172)

### For evaluation

Best submission

[28/05/2023 10:30:05 - 100.0%](https://inginious.info.ucl.ac.be/course/LINGI2172/lecture3_questions#)

Lecture 3: Questions

Collapse context

---

**Question 1: Equivalence under NULLs**

Note that under set operators, NULL=NULL, but that under join operators, the choice was made in common query languages not to match NULLs with NULLs.

Assume given two relations R1(A,B) and R2(B,C). Indicate all expressions that are equivalent if R1 and R2 do not contain NULLs, but that are no longer equivalent if either R1, R2 or both contain a NULL value.

![Untitled](Lecture%203_%20Questions%20-%20%5BLINFO2172%5D%20Databases%20_%20ING%20956b66710db5441aba28cd0a4d66f1ed/Untitled.png)

<aside>
💡 Tuples are considered identical iff their values are identical, where NULL is considered identical only to NULL.

</aside>

<aside>
💡 No tuples included with a NULL value in the common attribute

</aside>

**Question 2: Equivalence under NULLs**

Indicate which of the following expressions are equivalent, assuming that NULLs are possible; the relations have schema R1(A,B), R2(B,C).

![Untitled](Lecture%203_%20Questions%20-%20%5BLINFO2172%5D%20Databases%20_%20ING%20956b66710db5441aba28cd0a4d66f1ed/Untitled%201.png)

<aside>
💡 I still don’t understand this question.

</aside>

**Question 3: Results of a left outer join**

Does tuple ('x','z') in R1 have a corresponding tuple in R2?

Assume given the following query:

SELECT C, A FROM R1 LEFT OUTER JOIN R2 ON B

over a database with relations R1(A,B) and R2(B,C) that have the following tuples:

R1 ('x','x') ('x','z') ('y','x') ('y','y')

R2 ('x', 'x') ('x', 'y') ('y', 'x') ('y', 'y')

Indicate which tuples are in the output of this query.

('y','y'), exactly 1 time

(***NULL,'x')***

***('y','x'), at least once***

***('x','x'), exactly 1 time***

***('x','y'), at least once***

('x','x'), exactly 2 times

('y',NULL)

(NULL,'y')

***('y','y'), exactly 2 times***

('x',NULL)

**Question 4: Query optimization**

Assume given the following query:

SELECT A FROM R1, R2 WHERE R1.A='1' AND R1.B=R2.B AND R2.C='q'

over the same database as in the first exercise.

Indicate the number of tuples in the largest relation considered during the evaluation of this query, for the most naïve execution plan of the query; this is the plan that results from a direct translation of the query into relational algebra.

6

***9***

3

5

<aside>
💡 It seems that some information is missing.

</aside>

**Question 5: Query optimization**

Reconsider the query of the previous question. Assume that we rewrite the query plan, such that selection is pushed as deeply as possible. What is the size of the largest relation considered during the execution of this query for the most efficient query plan that can be obtained by pushing selection?

2

1

9

***3***

<aside>
💡 It seems that some information is missing.

</aside>

**Question 6: Query optimization**

Pushing projection can increase performance because...

***The number of attributes in temporary relations becomes smaller, which means more temporary relations can be stored in the main memory of the computer***

***The number of tuples in temporary relations can become smaller; as a result, later operators can work on smaller tables.***

The projection is executed on a smaller table.

The number of attributes in temporary relations becomes smaller, which means that the selection has to consider less attributes.

<aside>
💡 In the last option, the process only takes into account the attribute used for joining, regardless of whether or not we perform a projection operation.

</aside>