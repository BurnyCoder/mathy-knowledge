## Axioms of ZF

### Extensionality

$$  
\forall x \forall y \left[ \forall z \left( z \in x \leftrightarrow z \in y \right) \to x = y \right]  
$$

This axiom asserts that when sets $x$ and $y$ have the same members, they are the same set.

---

### Null Set

The next axiom asserts the existence of the empty set:

$$  
\exists x \neg \exists y \left( y \in x \right)  
$$

Since it is provable from this axiom and the previous axiom that there is a unique such set, we may introduce the notation $\emptyset$ to denote it.

---

### Pairs

The next axiom asserts that given any sets $x$ and $y$, there exists a pair set of $x$ and $y$, i.e., a set which has only $x$ and $y$ as members:

$$  
\forall x \forall y \exists z \forall w \left( w \in z \leftrightarrow w = x \lor w = y \right)  
$$

Since it is provable that there is a unique pair set for each given $x$ and $y$, we introduce the notation ${x, y}$ to denote it.

In the particular case when $x = y$, the axiom asserts the existence of the singleton ${x}$, namely the set having $x$ as its unique member.

---

### Power Set

The next axiom asserts that for any set $x$, there is a set $y$ which contains as members all those sets whose members are also elements of $x$, i.e., $y$ contains all of the subsets of $x$:

$$  
\forall x \exists y \forall z \left[ z \in y \leftrightarrow \forall w \left( w \in z \to w \in x \right) \right]  
$$

Since every set provably has a unique power set, we introduce the notation $\mathcal{P}(x)$ to denote it.

Note also that we may define the notion “$x$ is a subset of $y$,” written $x \subseteq y$, as:

$$  
\forall z \left( z \in x \to z \in y \right)  
$$

Then we may simplify the statement of the Power Set Axiom as follows:

$$  
\forall x \exists y \forall z \left( z \in y \leftrightarrow z \subseteq x \right)  
$$

---

### Unions

The next axiom asserts that for any given set $x$, there is a set $y$ which has as members all of the members of all of the members of $x$:

$$  
\forall x \exists y \forall z \left[ z \in y \leftrightarrow \exists w \left( w \in x \land z \in w \right) \right]  
$$

Since it is provable that there is a unique union of any set $x$, we introduce the notation $\bigcup x$ to denote it.

---

### Infinity

The next axiom asserts the existence of an infinite set, i.e., a set with an infinite number of members:

$$  
\exists x \left[ \emptyset \in x \land \forall y \left( y \in x \to \bigcup {y, {y}} \in x \right) \right]  
$$

We may think of this as follows. Let us define the union of $x$ and $y$, written $x \cup y$, as the union of the pair set of $x$ and $y$, i.e., as:

$$  
\bigcup {x, y}  
$$

Then the Axiom of Infinity asserts that there is a set $x$ which contains $\emptyset$ as a member and which is such that whenever a set $y$ is a member of $x$, then $y \cup {y}$ is also a member of $x$.

Consequently, this axiom guarantees the existence of a set of the following form:

$$  
\left\{
\emptyset,
\{\emptyset\},
\{\emptyset, \{\emptyset\}\},
\{\emptyset, \{\emptyset\}, \{\emptyset, \{\emptyset\}\}\},
\dots
\right\}
$$

Notice that the second element, ${\emptyset}$, is in this set because:

1. The fact that $\emptyset$ is in the set implies that $\emptyset \cup {\emptyset}$ is in the set.
    
2. $\emptyset \cup {\emptyset}$ just is ${\emptyset}$.
    

Similarly, the third element, ${\emptyset, {\emptyset}}$, is in this set because:

1. The fact that ${\emptyset}$ is in the set implies that ${\emptyset} \cup {{\emptyset}}$ is in the set.
    
2. ${\emptyset} \cup {{\emptyset}}$ just is ${\emptyset, {\emptyset}}$.
    

And so forth.

---

### Separation Schema

Next is the Separation Schema, which is a formula-pattern that uses a metavariable, in this case $\psi$, to describe an infinite list of axioms — one axiom for each formula of the language of set theory with at least one free variable.

Every instance of the Separation Schema asserts the existence of a set that contains the elements of a given set $w$ that satisfy a certain condition, which is given by a formula $\psi$.

That is, suppose that:

$$  
\psi(x, u_1, \dots, u_k)  
$$

is a formula of the language of set theory that has $x$ free and may or may not have $u_1, \dots, u_k$ free.

Then the Separation Schema for the condition $\psi$ asserts:

$$  
\forall u_1 \dots \forall u_k  
\left[  
\forall w \exists v \forall r  
\left(  
r \in v \leftrightarrow r \in w \land \psi(r, u_1, \dots, u_k)  
\right)  
\right]  
$$

In other words, given sets $w$ and $u_1, \dots, u_k$, there exists a set $v$ which has as members precisely the members $r$ of $w$ which satisfy the formula:

$$  
\psi(r, u_1, \dots, u_k)  
$$

---

### Replacement Schema

Next is the Replacement Schema, which is also a formula-pattern that uses a metavariable, in this case $\phi$, to describe an infinite list of axioms — one axiom for each formula of the language of set theory with at least two free variables.

Suppose that:

$$  
\phi(x, y, u_1, \dots, u_k)  
$$

is a formula with $x$ and $y$ free, and in which $u_1, \dots, u_k$ may or may not be free.

Then the instance of the Replacement Schema given by $\phi(x, y, u_1, \dots, u_k)$ is the following axiom:

$$  
\forall u_1 \dots \forall u_k  
\left[  
\forall x \exists! y , \phi(x, y, u_1, \dots, u_k)  
\to  
\forall w \exists v \forall r  
\left(  
r \in v \leftrightarrow  
\exists s  
\left(  
s \in w \land \phi(s, r, u_1, \dots, u_k)  
\right)  
\right)  
\right]  
$$

In other words, if we know that $\phi$ is a functional formula, which relates each set $x$ to a unique set $y$, then if we are given a set $w$, we can form a new set $v$ as follows: collect all of the sets to which the members of $w$ are uniquely related by $\phi$.

Note that the Replacement Schema can take you “out of” the set $w$ when forming the set $v$. The elements of $v$ need not be elements of $w$.

By contrast, the Separation Schema of Zermelo only yields subsets of the given set $w$.

---

### Regularity

The final axiom asserts that every set is well-founded:

$$  
\forall x  
\left[  
x \neq \emptyset  
\to  
\exists y  
\left(  
y \in x  
\land  
\forall z  
\left(  
z \in x \to \neg(z \in y)  
\right)  
\right)  
\right]  
$$

A member $y$ of a set $x$ with this property is called a minimal element.

This axiom rules out the existence of circular chains of sets, such as:

$$  
x \in y \land y \in z \land z \in x  
$$

as well as infinitely descending chains of sets, such as:

$$  
\dots \in x_3 \in x_2 \in x_1 \in x_0  
$$

### Well-ordering (choice)
 https://en.wikipedia.org/wiki/Axiom_of_choice

^[https://en.wikipedia.org/wiki/Zermelo%E2%80%93Fraenkel_set_theory] ^[https://plato.stanford.edu/entries/set-theory/zf.html] ^[https://ncatlab.org/nlab/show/ZFC]