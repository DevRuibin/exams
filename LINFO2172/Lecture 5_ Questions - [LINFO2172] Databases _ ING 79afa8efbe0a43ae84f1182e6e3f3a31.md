# Lecture 5_ Questions - [LINFO2172] Databases _ INGInious

Class: LINFO2172
Created: May 28, 2023 8:06 AM
Reviewed: No
Type: Reading

### Information

| Author(s) | Siegfried Nijssen |
| --- | --- |
| Deadline | No deadline |
| Status | Succeeded |
| Grade | 100% |
| Grading weight | 1.0 |
| Attempts | 22 |
| Submission limit | No limitation |

### Submitting as

**Ruibin Zhang**

[Group management](https://inginious.info.ucl.ac.be/group/LINGI2172)

### For evaluation

Best submission

[28/05/2023 07:58:41 - 100.0%](https://inginious.info.ucl.ac.be/course/LINGI2172/lecture7_questions#)

Lecture 5: Questions

Collapse context

---

**Question 1: Functional Dependencies: Full Functional Dependencies**

Given is the following table:

| A | B | C | D |
| --- | --- | --- | --- |
| a1 | b1 | c1 | d1 |
| a1 | b2 | c2 | d1 |
| a2 | b1 | c2 | d2 |
| a2 | b1 | c2 | d2 |

Indicate which statements correspond to full and non-trivial functional dependencies in this table.

B C -> B

***B D -> C***

A B -> D

A B -> C

**Question 2: Functional Dependencies: Full Functional Dependencies**

Given is the following table:

| A | B | C | D |
| --- | --- | --- | --- |
| a1 | b1 | c1 | d1 |
| a2 | b1 | c2 | d1 |
| a3 | b1 | c2 | d2 |
| a4 | b1 | c1 | d2 |

Indicate which statements correspond to full and non-trivial functional dependencies in this table.

B -> A

***C D -> A***

***C -> B***

A C -> D

**Question 3: Implied Functional Dependencies**

Given are the following functional dependencies:

A -> B C D

B -> C

C -> D

C D -> B

Indicate which functional dependencies are implied by these functional dependencies.

***C -> B***

***B -> D***

D -> B

***A -> D***

**Question 4: Equivalence of functional dependencies**

Given are the following functional dependencies:

A -> B C D

C -> D

D -> C

B -> E

Indicate which sets of functional dependencies are equivalent to this set of functional dependencies.

***A -> B C***

***C -> D***

***D -> C***

***B -> E***

A -> B C D E

C -> D

D C -> C

B -> E

***A -> B D***

***C -> D***

***D -> C***

***B -> E***

***A -> B C D E***

***C -> D***

***D -> C***

B -> E

**Question 5: 2nd Normal form**

✓

×Close

The primary key of this relation is {A}, the non-prime attributes are {B,C,D}

The keys in this relation are {A,B} and {C}, the prime attributes are {D,E}.

The primary key of this relation is {A,B}, the non-prime attributes are {C,D,E}.

Below are given sets of functional dependencies; indicate for each whether a table with those functional dependencies is in 2nd normal form.

Note that primary keys can be derived from functional dependencies!

***A B -> C D***

***A -> B***

A B -> C D E

B -> E

***A B -> C D E***

***C -> A B D E***

***D -> E***

A B -> C

C -> D

C -> E

A B -> C D

A -> C

**Question 6: 3rd Normal Form**

✓

×Close

Note that D is a prime attribute (part of a key), and hence C -> D is FD with a prime attribute on the right-hand side.

Below are given sets of functional dependencies; indicate for each whether a table with those functional dependencies is in 3rd normal form.

***A B -> C D***

***A -> B***

***A B -> C D***

***C -> D***

***A D -> B C***

> AD is the primary key. AB → CD ⇒ AB →C & AB → D
> 

A B -> C

C -> D

C -> E

A B -> C D E

C -> A B D E

D -> E

<aside>
💡 A relation is in the third normal form iff for every nontrivial full functional dependency X → A in R, either X is a key or A is a prime attribute.

</aside>

**Question 7: Given are these functional dependencies in a relation R: (A, B → C), (C → B), (C → D), (C → E). Which of the following set of relations is a valid decomposition in third normal form?**

***R1(A,B,C), R2(C,D,E)***

R1(A,B), R2(B,C), R3(C,D,E)

***R1(A,C), R2(B,C), R3(C,D), R4(C,E)***

***R1(A,B,C), R2(C,D), R3(C,E)***

**Question 8: Given are these functional dependencies in a relation R: (A, B → C), (C → B), (C → D), (C → E). (Same as in the previous exercise.) Which of the following set of relations is a valid decomposition in Boys-Codd normal form?**

***R1(A,C), R2(B,C), R3(C,D), R4(C,E)***

R1(A,B), R2(B,C), R3(C,D,E)

R1(A,B,C), R2(C,D,E)

R1(A,B,C), R2(C,D), R3(C,E)

<aside>
💡 A relation is in Boys-Codd normal form iff for every nontrivial full functional dependency X → A in R, X is key.

</aside>