> Based on the work of Tobias Lowenthal.

# Question 1

1. `a ( ) . + -`
2. see ![answer for question 1.2](TP2/1.png)

**1.4**

-a+a with left-most derivation :

- Can do S =5=> -S =4=> -S+S =1=> -a+S =1=> -a+a 5411
- But also S =4=> S+S =5=> -S+S =1=> -a+S =1=> -a+a 4511
- Both leftmost derivation but different syntax tree

# Question 2

**2.1**

```
E → E + T | E - T | T
T → T ∗ F | T / F | F
F → ( E ) | Number | Identifier
```

**2.2**

For `3 + 4 / 5`:

```
E   -> E + T
    -> T + T
    -> F + T
    -> 3 + T
    -> 3 + T / F
    -> 3 + F / F
    -> 3 + 4 / F
    -> 3 + 4 / 5
```

AST:

```
  +
 / \
 3  /
   / \
  4   5
```

or

```
    Additive
    /   |   \
   3    +    Multiplicative
                /   |   \
               4    /    5
```

**2.3**

Add a new operator "<" for the grammar:

```
E -> H < H | H
H → H + T | H - T | T
T → T ∗ F | T / F | F
F → ( E ) | Number | Identifier
```

Rule for `4 + 7 < 3 + 4 / 5`

```
E   -> H < H              // rule 1
    -> H + T < H          // rule 3
    -> T + T < H          // rule 5
    -> F + T < H          // rule 8
    -> 4 + T < H          // rule 10
    -> 4 + F < H          // rule 8
    -> 4 + 7 < H          // rule 10
    -> 4 + 7 < H + T      // rule 3
    -> 4 + 7 < T + T      // rule 5
    -> 4 + 7 < F + T      // rule 8
    -> 4 + 7 < 3 + T      // rule 10
    -> 4 + 7 < 3 + T / F  // rule 7
    -> 4 + 7 < 3 + F / F  // rule 8
    -> 4 + 7 < 3 + 4 / F  // rule 10
    -> 4 + 7 < 3 + 4 / 5  // rule 10
```

AST:

```
    <
   / \
  +   +
 / \ / \
4  7 3  /
      / \
     4   5
```

# Question 3

Here is a CFG for regular expressions over the alphabet {a, b}:

Grammar:

```
S -> R                          (1)
R -> R + R | RR | R* | T        (2, 3, 4, 5)
T -> (R) | a | b                (6, 7, 8)
```

Note that we are suing the plus-symbol `+` to represent the choice in regular expressions to
avoid confusion with the "|" used by the CFG itself.

Run the NTA of this grammar for the input `a + (b*)`

```
initial state:                      ( a + (b*), S, epsilon)
Rule 1 to expand S:                 ( a + (b*), R, 1)
Rule 2 to expand R:                 ( a + (b*), R+R, 12)
Rule 5 to expand R:                 ( a + (b*), T+R, 125)
Rule 7 to expand T:                 ( a + (b*), a+R, 1257)
Match a:                            ( + (b*), +R, 1257)
Match +:                            (  (b*), R, 1257)
Rule 5 to expand R:                 ( (b*), T, 12575)
Rule 6 to expand T:                 ( (b*), (R), 125756)
Match (:                            ( b*), R), 125756)
Rule 4 to expand R:                 ( b*), R*), 1257564)
Rule 5 to expand R:                 ( b*), T*), 12575645)
Rule 8 to expand T:                 ( b*), b*), 125756458)
Match b:                            ( *), *), 125756458)
Match *:                            ( ), ), 125756458)
Match ):                            ( , , 125756458)

```

# Question 4

**4.1**

$$fist_1(ab) = \{a\}$$
$$fist_1(ac) = \{a\}$$
$$first_2(ab) = \{ab\}$$
$$first_2(ac) = \{ac\}$$
$$fist_1(ab) \cap first_1(ac) = \{a\} != \emptyset$$
$$fist_2(ab) \cap first_2(ac) = \emptyset$$

So the grammar is not LL(1), but it is LL(2).

**4.2**

```
S -> aB
B -> b | c
```

**4.3**

`S -> abcdef | abcdeg`


