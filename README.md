**Important**: since github markdown doesn't support LaTeX, view the complete note in the following link instead: <https://rawgit.com/oldfatcrab/PMATH336/master/PMATH336_note.html>

--------------------------------------------------------------------------------

# Table of Content

- [Chapter 0: Course Administration](#toc_1) (May 02)
- [Chapter 1: Groups](#toc_2) (May 02)
    - [1.1 Definitions and examples](#toc_3) (May 02)
    - [1.2 Subgroups](#toc_4) (May 06)
    - [1.3 Finite groups](#toc_5) (May 13)
    - [1.4 Cyclic groups](#toc_6) (May 18)

--------------------------------------------------------------------------------

_2016/05/02_

# Chapter 0: Course Administration
- Course structure
    - Group Theory Basics
        - Examples
        - Axioms
        - Subgroups and Lagrange's Theorem
        - Cyclic groups
        - Permutation groups
        - Normal subgroups
        - quotients
        - homomorphisms
        - Isomorphism theorems
        - automorphism groups and conjugation
    - Group Actions
        - The orbit-statiliser theorem
        - Cauchy's theorem
        - Burnside's lemma
        - P&ograve;lya enumeration
        - the class equation
    - Other Topics
        - Platonic solids
        - classification of finite abelian groups
        - cryptography
        - application to physics (if time permitting)
- Grading
    - 6 assignments: 30%
    - Midterm: 20%
    - Final: 50%
- Office
    - MC 5427
    - Monday 14:00-16:00, Thursday 15:00-17:00, or by appointment

--------------------------------------------------------------------------------

# Chapter 1: Groups

## 1.1 Definitions and examples:

- Let $G$ be a non-empty set.
    - Def'n: A binary operation on $G$ is a map that
        - $G \times G \rightarrow G$
        - $(a,b) \mapsto a\star b$ or $a\cdot b$ or $ab$ (notation)
    - A binary operation is often called a **product**
- Ex 1)
    - $G=\mathbb{Z}$ and
    - and $+: \mathbb{Z}\times \mathbb{Z} \rightarrow \mathbb{Z}$, $(m,n) \mapsto m+n$
    - or $\cdot: \mathbb{Z}\times \mathbb{Z} \rightarrow \mathbb{Z}$, $(a,b) \mapsto ab$
- Ex 2)
    - $G=\mathbb{R}^3$
    - and $ +: \mathbb{R}^3 \times \mathbb{R}^3 \rightarrow \mathbb{R}^3, ((x_1, y_1, z_1), (x_2, y_2, z_2)) \mapsto (x_1+x_2, y_1+y_2, z_1+z_2)$
    - and $\times: \mathbb{R}^3 \times \mathbb{R}^3 \rightarrow \mathbb{R}^3, ((x_1, y_1, z_1), (x_2, y_2, z_2)) \mapsto (x_1, y_1, z_1) \cdot (x_2, y_2, z_2)$
    - but $\dot: \mathbb{R}^3 \times \mathbb{R}^3  \rightarrow \mathbb{R}, ((x_1, y_1, z_1), (x_2, y_2, z_2)) \mapsto (x_1x_2, y_1y_2, z_1z_2)$ is **not** a binary operation because the target space is not $G=\mathbb{R}^3$
- Def'n (**Groups**): Let $G$ be a non-empty set with a binary operation, $G\times G\rightarrow G$, then $G$ is a **group** if the binary operation has the following properties:
    - (i) (**Associativity**): $a(bc) = (ab)c$, $\forall a,b,c \in G$
    - (ii) (**Identity**): $\exists e \in G$ such that: $ea = ae =a, \forall a$ in $G$
    - (iii) (**Inverse**): $\forall a \in G$, $\exists a^{-1} \in G$ such that: $aa^{-1} = a^{-1} a = e$
- Ex 1)
    - The integers: $(\mathbb{Z},+) \leadsto $ this is a group
    - **HERE**: $G = \mathbb{Z}$ and $+: \mathbb{Z}\times\mathbb{Z} \rightarrow \mathbb{Z}, (m,n) \mapsto m+n$
    - Does $+$ satisfy properties (i) to (iii)?
        - (i) Let $m, n, r \in \mathbb{Z}$, then:
            - $m+(n+r) = (m+n)+r$ ? YES!
        - (ii) Identity of $+$ is $0 \in \mathbb{Z}$
            - because $0 + m = m + 0 = m, \forall m \in \mathbb{Z}$
        - (iii) $\forall m \in \mathbb{Z}$, we have that
            - $m + (-m) = (-m) + m = 0$
            - $\Rightarrow -m \in \mathbb{Z}$ is the inverse of $m \in \mathbb{Z}$
        - Thus, $(\mathbb{Z},+)$ is a group.
- Ex 2)
    - The integers: $(\mathbb{Z},\cdot)\leadsto$ this is a group
    - **HERE**: $G = \mathbb{Z}$ and $\cdot: \mathbb{Z}\times\mathbb{Z} \rightarrow \mathbb{Z}, (m,n) \mapsto m\cdot n$
    - Does $\cdot$ satisfy properties (i) to (iii)?
        - (i) Let $m, n, r \in \mathbb{Z}$, then:
            - $m\cdot(n\cdot r) = (m\cdot n)\cdot r$ ? YES!
        - (ii) Identity of $\cdot$ is $1 \in \mathbb{Z}$
            - because $1 \cdot m = m \cdot 1 = m$, $\forall m \in \mathbb{Z}$
        - (iii) $\forall m \in \mathbb{Z}$, the inverse of m with respect to multiplication is $\frac{1}{m}$ (if $m \neq 0$), but $\frac{1}{m} \notin \mathbb{Z}$ if $m\neq\pm1$. So property (iii) fails!
        - Thus, $(\mathbb{Z},\cdot)$ is not a group.
- Ex 3)
    - $G = \{1, -1\}$ set of 2 elements with the binary operation given by:

| $\cdot$ | $1$  | $-1$ |
|---------|----|----|
| $1$       | $1$  | $-1$ |
| $-1$      | $-1$ | $1$  |

- (continue)
    - Note that $\cdot$ is just the usual product in $\mathbb{R}$ restricted to element in $G$. Then $G$ is a group because:
        - (i) $\cdot$ is associative because multiplication in $\mathbb{R}$ is associative
        - (ii) $1$ is the identity.
        - (iii) From the table, we see that $1$ is the inverse of $1$ and $-1$ is the inverse of $-1\leadsto$ every element in $G$ has an inverse.
- Ex 4)
    - $(\mathbb{Q}, +)$ is a group (exercise)
- Ex 5)
    - $ (\mathbb{Q}^*, \cdot)$ is a group where $\mathbb{Q}^* = \mathbb{Q}\setminus\{0\}$
    - Indeed:
        - (i) Multiplication in $\mathbb{Q}^*$ is associative as in $\mathbb{Z}$ and $\mathbb{R}$
        - (ii) $1 \in \mathbb{Q}^*$ is the identity with respect to \dot.
        - (iii) $\forall \frac{a}{b} \in \mathbb{Q}^*$, we have that $\frac{b}{a} \in \mathbb{Q}^*$ and $\frac{a}{b} \cdot \frac{b}{a} = \frac{b}{a}\cdot \frac{a}{b} = 1 \Rightarrow \frac{a}{b}^{-1} = \frac{b}{a} \Rightarrow$ every element in $\mathbb{Q}^*$ has an inverse
    - Note:
        - $(\mathbb{Q}, \cdot)$ is **not** a group because even though (i) and (ii) hold, property (iii) fails for $0 \in \mathbb{Q}$
- Ex 6)
    - $(\mathbb{R}, +)$ and $(\mathbb{C}, +)$ are groups
- Ex 7)
    - $(\mathbb{R}^*, \cdot)$ and $(\mathbb{C}^*, \cdot)$ are groups (where $\mathbb{R}^* = \mathbb{R}\setminus\{0\}$ and $\mathbb{C}^* = \mathbb{C}\setminus\{0\})$
- Ex 8)
    - $(\{1, i, -1, -1\}, \cdot)$ is a group, where $i \in \mathbb{C}$ such that $i^2 = -1$. Here:

| $\cdot$ | $1$  | $i$  | $-1$ | $-i$ |
|---------|----|----|----|----|
| $1    $   |$ 1  $|$ i$  | $-1$ | $-i$ |
| $i   $    |$ i  $|$ -1$ | $-i$ | $1 $ |
| $-1 $     |$ -1 $|$ -i$ | $1 $ | $i $ |
| $-i$      |$ -i $|$ 1 $ | $i $ | $1 $ |

_2016/05/04_

- Review from last lecture:
	- Def'n (**Groups**): Let $G$ be a non-empty set with a binary operation, $G\times G\rightarrow G$, then $G$ is a **group** if the binary operation has the following properties:
	    - (i) (**Associativity**): $a(bc) = (ab)c$, $\forall a,b,c \in G$
	    - (ii) (**Identity**): $\exists e \in G$ such that: $ea = ae =a, \forall a$ in $G$
	    - (iii) (**Inverse**): $\forall a \in G$, $\exists a^{-1} \in G$ such that: $aa^{-1} = a^{-1} a = e$
- Note: Properties (i)-(iii) in the def'n are called the **group axioms**
- Ex 9) **Integer module n**: $\mathbb{Z}_n$
	- In $\mathbb{Z}_n$, two integer $r$ and $s$ are equivalent if $r = s+an$, for same $a$ in $\mathbb{Z}$, this is written as $r \equiv s$ (mod $n$)
	- e.g.:
 		- $\mathbb{Z}_3 = \{\overline{0}, \overline{1}, \overline{2}\}$
 		- $\overline{0} \equiv \{0, 3, -3, 6, \cdots\} \equiv \overline{3}$
 		- $\overline{1} \equiv \{1, 4, -2, 7, \cdots\} \equiv \overline{4}$
 		- $\overline{2} \equiv \{2, 5, -1, 8, \cdots\} \equiv \overline{5}$
	- $\forall F, F' \in \mathbb{Z}_n$, we set:
		- $\overline{r} + \overline{r_1} = \overline{r+r_1}$, and
		- $\overline{r} \cdot \overline{r_1} = \overline{r \cdot r1}$
	- $(\mathbb{Z}_n, +)$: since $+$ is associative in $\mathbb{Z}$, it is also associative with $\mathbb{Z}_n$. Moreover, $\overline{0}$ is the identity for $+$. finally, $\overline{-r}$ is **inverse** of $F$ with respect to $+$. We will denote $\overline{-r}$ by $-\overline{r} \Rightarrow (\mathbb{Z}_n, +)$ is a group
	- $(\mathbb{Z}_n, \cdot)$: Again, since $\cdot$ is associative in $\mathbb{Z}$, it is also associative in $\mathbb{Z}$,. And $\overline{1}$ is the identity for $\cdot$, however, not every element in $\mathbb{Z}_n$ has an inverse with respect to $\cdot$. In fact, recall that $F \in \mathbb{Z}_n$ has a multiplicative inverse iff $gcd(r,n) = 1$. I.e. $\exists \overline s \in \mathbb{Z}_n$ such that $\overline r \cdot \overline s = \overline s \cdot \overline r = \overline 1$ iff $gcd(r, n) = 1$
	- If an element $\overline r \in \mathbb{Z}_n$ has an inverse in $\mathbb{Z}_n$, it is called a **unit**.
	- Set $\mathbb{Z}_n^* = \{\text{units in }\mathbb{Z}_n\} = \{F\in \mathbb{Z}_n \mid gcd(r,n)=1\}$. Then, $(\mathbb{Z}_n^*, \cdot)$ is a group
		- E.g. $\mathbb{Z}_6 = \{\overline 1, \overline 2, \overline 3, \overline 4, \overline 5, \overline 6\}$ and $\mathbb{Z}_6^* = \{\overline 1, \overline 5\}$
	- The Cayley table for $(\mathbb{Z}_6, \cdot)$ is:

| $\cdot$ | $\overline 1$  | $\overline 5$ |
|---------|----|----|
| $\overline 1$ | $\overline 1$ | $\overline 5$ |
| $\overline 5$ | $\overline 5$  | $\overline 1$ |

- Def'n: Let $(G, \cdot)$ be a group, the **order of the group** $G$ is denoted $\mid G \mid$, is the number of element in the group
	- Remark: If the binary operation is clear, we write $G$ instead of $(G, \cdot)$
	- E.g.:
		- $(\mathbb{Z}, +) \Rightarrow \mid\mathbb{Z}\mid = \infty$
		- $(\mathbb{Z}_6,+) \Rightarrow \mid\mathbb{Z}_6\mid = 6$
		- $(\mathbb{Z}_6^*,\cdot) \Rightarrow \mid\mathbb{Z}_6^* \mid = 2$
- Aside: There is another important set of objets in abstract algebra, which corresponds to rings (with identity):
	- Def'n: A **ring** (with identity) is a non-empty set $G$ together with **two** binary operations $+$, $\cdot$, such that:
		- 1) $(G,+)$ is a group (i.e. $+$ satisfies properties (i)-(iii)
		- 2) $(G,\cdot)$ is such that $\cdot$ satisfies (i) and (iii) 
		- 3) $+$ and $\cdot$ satisfy the distributive lays: $(a+b)\cdot c = a\cdot c+b\cdot c, \forall a,b,c \in G$
	- E.g. $(\mathbb{Z}, +, \cdot)$, $(\mathbb{R}, +, \cdot)$, $(\mathbb{C}, +, \cdot)$, $(\mathbb{Q}, +, \cdot)$ , $(\mathbb{Z}_6, +, \cdot)$ etc.
	- In a ring, the elements that have inverses with respect to multiplication are called **units**
- Def'n: A group $(G, \cdot)$ is called **abelian** if the binary operation is **commutative**: $a \cdot b = b \cdot a, \forall a,b \in G$
	- E.g. $(\mathbb{Z}, +)$, $(\mathbb{R}, +)$, $(\mathbb{C}, +)$, $(\mathbb{Q}, +)$ , $(\mathbb{Z}_6, +)$ etc.
	- However, not every group is abelian!
		- E.g. Consider $G = GL(n, \mathbb{R}) = \{A\in M_{n\times n}(\mathbb{R}) \mid A\text{ is invertible}\} = \{A\in M_{n\times n}(\mathbb{R}) | \det A \neq 0\} $
	- Note that $\exists$ natural operations on $n\times n$ matrices: addition and multiplication. Let $A, B \in M_{n\times n}(\mathbb{R})$. Then:
		- $A+B,\, A\cdot B \in M_{n\times n}(\mathbb{R})$
		- $\Rightarrow +$, $\cdot$ are binary operations for $M_{n\times n}(\mathbb{R})$
		- However, if $A, B \in G$, although $A\cdot B \in G$, may not have $A+B \in G$ (e.g. $a\in G$ so that $0\in G$, but $A+(-A)=0 \notin G$) $\Rightarrow$ $+$ is not a binary operation with for $G$
		- Consider $(G, \cdot)$. Then it is a group (exercise) where the identity is the nxn identity matrix $I_{n\times n}$. But, $(G, \cdot)$ is **not** abelian because $AB \neq BA$ for most $A,B \in G$
	- A group $(G, \cdot)$ is called **non-abelian** if it is not abelian.
- **Some basic properties**:
	- 1) The identity element $e$ in a group $(G, \cdot)$ is unique
	- 2) The inverse of an element in a group $(G, \cdot)$ is unique

_2016/05/06_

- Review:
	- Def'n (**Groups**): Let $G$ be a non-empty set with a binary operation, $G\times G\rightarrow G$, then $G$ is a **group** if the binary operation has the following properties:
	    - (i) (**Associativity**): $a(bc) = (ab)c$, $\forall a,b,c \in G$
	    - (ii) (**Identity**): $\exists e \in G$ such that: $ea = ae =a, \forall a$ in $G$
	    - (iii) (**Inverse**): $\forall a \in G$, $\exists a^{-1} \in G$ such that: $aa^{-1} = a^{-1} a = e$
	- **Some basic properties**:
		- 1) (**Uniqueness of identity**) The identity element $e$ in a group $(G, \cdot)$ is unique
		- 2) (**Uniqueness of inverses**) The inverse of an element in a group $(G, \cdot)$ is unique
- Proof of above identities:
	- 1) (Uniqueness of identity)
		- Suppose $\exists e, f \in G$ such that $ae = ea = a$ and $af = fa = a, \forall a \in G$.
		- In particular, since  $f\in G$, we have that $f = fe$ because $e$ is an identity
		- Similarly, because $e\in G$ and $f$ is an identity, $fe = e$
		- $\Rightarrow f=fe=e$
	- 2) (Uniqueness of inverses)
		- Let $a\in G$. Suppose that a has **two** inverses in $G$, say $a^{-1}$ and $b$. Therefore, by property (iii), we have: $aa^{-1} = a^{-1} a = e$ and $ab = ba = e$
		- Then $a^{-1} = a^{-1}e = a^{-1}(ab) = (a^{-1}a)b = eb = b$
		- $\Rightarrow a^{-1}=b$
- Using these properties, we obtain:
	- 3) $e{-1}=e$
	- 4) $(ab)^{-1}=b^{-1}a^{-1},\forall a,b \in G$
	- 5) $(a^{-1})^{-1}=a,\forall a \in G$
	- 6) $(a_1a_2\cdots a_n)^{-1} = a_n^{-1}\cdots a_2^{-1}a_1^{-1}$
	- 7) (Cancellation Property) Let $a,b,c\in G$ with $G$ a group. If ab = ac, then b=c. If ba=ca, then b = c.
- Proof:
	- 3) 
		- By uniqueness of the inverse, it is enough to check that $ee = ee = e$ to proof that $e^{-1}=e$. But this is true by property (ii).
	- 4)
		- By uniqueness of the inverse, it is enough to check that $ab(b^{-1}a^{-1}) = (b^{-1}a^{-1})ab = e$
		- By associatitivy, we have that $ab(b^{-1}a^{-1} = a(bb^{-1})a^{-1} = aea^{-1} = (ae)a^{-1} = aa^{-1} = e$
		- Similarly, $(b^{-1}a^{-1})ab=b^{-1}(a^{-1}a)b=b^{-1}eb=(b^{-1}e)b=b^{-1}b=e$
		- $\Rightarrow (ab)^{-1}=b^{-1}a^{-1}$
		- Note: 
			- $GL(n,\mathbb{R})=$ all general linear group 
			- One would be tempted to think that $(ab)^{-1}=a^{-1}b^{-1}$ but this is false in general.
			- Example:
				- $(G,\cdot) = (GL(2,\mathbb{R}),\cdot)$
				- A = $\begin{pmatrix}1&2\\0&1\end{pmatrix}$ and B = $\begin{pmatrix}2&0\\0&3\end{pmatrix}$
				- $\Rightarrow AB = \begin{pmatrix}2&6\\0&3\end{pmatrix}$ and $(AB)^{-1}=\begin{pmatrix}\frac{1}{2}&-1\\ 0&\frac{1}{3} \end{pmatrix}$
				- But, $A^{-1}B^{-1} = \begin{pmatrix}\frac 1 2&-\frac 2 3\\0&\frac 1 3\end{pmatrix} \neq (AB)^{-1}$
				- Nonetheless, $B^{-1}A^{-1} = \begin{pmatrix}\frac{1}{2}&-1\\ 0&\frac{1}{3} \end{pmatrix} = (AB)^{-1}$
			- In fact, one can show that: $(ab)^{-1}=a^{-1}b^{-1},\forall a,b,\in G \Leftrightarrow G$ is abelian (Exercise).
	- 5) and 6)
		- Exercise in assignment 1
	- 7) 
		- Suppose that $ab = ac$. Then, since $G$ is a group, $\exists a^{-1}\in G$ such that $aa^{-1}=a^{-1}a=e$
		- Therefore $a^{-1}(ab)=(a^{-1}a)b=eb=b$
		- Similarly, $a^{-1}(ac)=c$.
		- But, $ab=ac$, so that $a^{-1}(ab)=a^{-1}(ac)=c$
		- The proof of 2nd cancellation property is similar

## 1.2 Subgroups

- Def'n: Let $G$ e a group. If a subset $H$ of $G$ is itself a group under the operation of $G$, we say that H is a **subgroup** of $G$.
- Note: the definition of a subgroup implies that subset it **is closed under the operation in G**. I.e. $\forall a,b\in H$, then $ab\in H$. This ensures that restriction of the binary operation $G\times G\rightarrow G$ is again a binary operation taking $H\times H\rightarrow H$. However, a subset of a group of $G$ may not be closed under the operation on $G$.
	- E.g. $(M_{n\times n}(\mathbb{R}), +)$ is a group and $GL(n,\mathbb R)=\{A\in M_{n\times n}(\mathbb R) \mid \det A\ne 0\} \subset M_{nxn}(\mathbb R)$, but $GL(n, \mathbb R)$ is not closed under $+$ (e.g. $\forall A \in GL(n,\mathbb R), -A \in GL(n,\mathbb R)$) but $A+(-A) \notin GL(n,\mathbb R)$
- We use the notation $H \vartriangleleft G$ (or $H<G$) to mean that H is a subgroup of $G$. (some authors use $H\trianglelefteq G$ and $H\vartriangleleft G$ indicates that $H \leq G$). If $H \leq G$, then H is called a **proper subgroup of G**. The singleton $\{e\}$ is a subgroup of $G$ called the **trivial subgroup**; a subgroup of $G$ that is not $\{e\}$ is called a **non-trivial subtroup of G**.
- How does one determine whether or not a subset $H$ of $G$ is a subgroup? There are 2 tests:
	- Theorem (**One-step subgroup test**): Let $H$ be a non-empty subset of a group $G$. If $ab^{-1}\in H,\forall a,b\in H$, then $H\vartriangleleft G$.

_2016/05/09_

- Review from previous lectures:
	- $(G,\cdot)$ is a group if:
		- operation is associative
		- (**Identity**): $\exists e\in G$ such that $ae = ea = a, \forall a\in G$
		- (**Inverses**): $\forall a \in G, \exists a^{-1} \in G$ such that $aa^{-1}=a^{-1}a=e$.
	- Subgroup: let $0\neq H\subset G$ such that $H$ itself is a group under the same operation as G
	- Note: It is implicit in the definition that $H$ is closed under the operation of $G$ (i.e., $\forall a,b \in H$, then $ab\in H$).
	- Theorem (**One-step subgroup test**): Let $G$ be a group and $H$ be a non-empty subset of $G$. Then, $H$ is a subgroup of $G$ if $[ab^{-1}\in H,\forall a,b\in H]\quad(*)$

- Proof of one-step subgroup test:
	- We first need to check that H is closed under the operation in G. Given then property that $ab^{-1} \in H, \forall a,b\in H $ if we can prove that, $\forall a,b \in H, b^{-1}\in H$, then $ab=a(b^{-1})_{-1}\in H$.
	- We first notice that $e\in H$, because $H$ has at least one element, say a, so that $e=aa^{-1}\in H$ (by $(*)$).
	- Also, $e^{-1} = e$. Thus, $\forall a \in H$, we have that $a^{-1} = ea^{-1}\in H$ (by $(*)$).
	- Finally, $\forall a,b\in H$, since $b^{-1}\in H$, we get that $ab=a(b^{-1})^{-1}\in H$ by $(*)$
	- $\Rightarrow H$ is closed under the operation
	- Note: we still to check that the restriction of the operation on $G$ satisfies the 3 group axioms. Since the operation is associative on $G$, it is also associative on $H$. And we have already seen that the identity and inverse axioms hold.

- Theorem (**Two-step subgroup test**) Let $G$ be a group and $H$ be a non-empty subset of $G$. Then $H$ is a subgroup of $G$ if $ab\in H \forall a,b\in H$ (H is closed under the operation on G), and $a^{-1} \in H, \forall a \in H$ (H is closed under inverse).
	- Proof: Let $a,b\in H$. Then $b^{-1} \in H$ so that $ab^{-1} \in H$. Thus, by one-step subgroup test, H is a subgroup.
		- Remark: The two-step subgroup test is useful if one already knows that **the subset $H$ of $G$ is clsed under the operation or clsed under inverses**, so that there then is only one thing left to check.
	- Ex 1)
		- $(\mathbb C, +) \leadsto (\mathbb Z^*, +) \vartriangleleft (\mathbb Q^*,+)\vartriangleleft (\mathbb R^*,+)\vartriangleleft (\mathbb C^*,+)$
		- $(\mathbb C, \cdot) \leadsto (\mathbb Q^*,\cdot)\vartriangleleft (\mathbb R^*,\cdot)\vartriangleleft (\mathbb C^*,\cdot)$
		- Note: $^*$ means without zero
	- Ex 2)
		- $(\{1,-1\}, \cdot)$ group with $\cdot$ the usual multiplication in $\mathbb C$
		- $(\{1,-1\}, \cdot)\vartriangleleft(\mathbb Q^*, \cdot)\vartriangleleft(\mathbb R^*, \cdot)\vartriangleleft(\mathbb C^*, \cdot)$
	- Ex 3)
		- $(\mathbb Z, +)$
		- $H=\{2m\mid m\in \mathbb Z\} \Rightarrow $ H is closed under $+$ since the sum of 2 even integers is even
		- Also, $\forall 2m \in H$, its inverse - $2m\in H \Rightarrow H$ is closed under inverse. Thus, $H \vartriangleleft (\mathbb Z,+)$ by the two-step subgroup test
	- Ex 4)
		- $(\mathbb Z_6,+) =\{\overline 0, \overline 1, \overline 2, \overline 3, \overline 4, \overline 5\}$
		- Then, $H = \{\overline 0, \overline 2, \overline 4\} \vartriangleleft \mathbb Z_6$
		- $(Z_6^*, \cdot) = {\overline 1, \overline 5} \leadsto $ the only proper subgroup of $Z_6^*$ is the trivial subgroup $H=\{\overline 1\}$
		- $(Z_{12}^*, \cdot) =\{\overline 1,\overline 5,\overline 7,\overline{11}\}$
	
	| $\cdot$ | $\overline 1$  | $\overline 5$ | $\overline 7$ | $\overline {11}$ |
	|---------|----|----|---|----|
	| $\overline 1$ | $\overline 1$ | $\overline 5$ | $\overline 7$ | $\overline{11} $ |
	| $\overline 5$ | $\overline 5$  | $\overline 1$ | $\overline{11}$ | $\overline 7$ |
	| $\overline 7$ | $\overline 7$  | $\overline{11}$ | $\overline 1$ | $\overline 5$ |
	| $\overline{11}$ | $\overline{11}$  | $\overline 7$ | $\overline 5$ | $\overline 1$ |

-	
	- 
		- Every element is inverse itself
		- $(\{\overline 1, \overline5\},\cdot), (\{\overline 1,\overline 7 \},\cdot), (\{\overline 1, \overline{11} \},\cdot), (\{\overline1 \},\cdot)\leftarrow$ These are the only proper subgroups of $(\mathbb Z_{12}^*, \cdot)$
	- Note: We have seen in the proof of the one-step subgroup test that if $H\vartriangleleft G$, then $e \in H$ where $e$ is the identity in $G$. However, since $H$ is closed under the operation on $G, \forall a\in H, ae = ea = a$ (since $e$ is the identity in $G$) $\Rightarrow e$ is an identity element in $H$ for the operation in $H$. So, because identity element are unique, $e$ is also the identity in $H$.
- Prop: Let $G$ be a group and $a\in G$. Set $\langle a\rangle:=\{a^m = aa\cdots a \mid m\in \mathbb Z\}$ Then $\langle a\rangle \vartriangleleft G$ called the **cyclic subgroup of $G$ generated by $a$**
	- Proof:
		- Let $a^m, a^{m'}\in \langle a\rangle$.
		- Then $(a^m)^{-1} = a^{-m}\in <a\rangle$, since $-m' \in \mathbb Z$.
		- Therefore $a^m (a^{m'})^{-1} = a^m a^{-m'} = a^{m-m'} \in \langle a\rangle$ since $m'\in Z$.
		- So, by the 1-step subgroup test, $\langle a\rangle \vartriangleleft G$
	- Ex 1)
		- $(\mathbb Z,+) \leadsto H=\{2m \mid m\in \mathbb Z\}=\langle 2\rangle$ since, using additive notation, $\langle 2\rangle = \{2+2+\cdots +2\mid m\in \mathbb Z\}$
	- Ex 2)
		- $(\mathbb Z_{12}^*, \cdot) = \{\overline 1,\overline 5,\overline 7,\overline{11}\}$
		- $\{1,5\}$ = $\langle\overline 5\rangle$ because $\langle\overline 5\rangle = \langle1, \overline 5, \overline 5^2, \overline 5^3, \cdots\rangle$
		- $\{\overline 1, \overline 7\}$
		- $\{\overline 1, \overline{11}\}$ 

_2016/05/11_

- Clarification from last lecture: 
	- Let $G$ be a group, and $a\in G$. We defined: $\langle a\rangle:=\{a^m\mid m\in \mathbb Z\}$ when $a^0:=e$ and $a^{-n} = a_{-1}\cdot a_{-1}\cdot \cdots a_{-1}$ if $n\in \mathbb N$. 
	- This means $a^{n}a^{-n}$ $= (a_{1}\cdot a_{1}\cdot \cdots a_{1})( a_{-1}\cdot a_{-1}\cdot \cdots a_{-1}) $ $= (a_{1}\cdot a_{1}\cdot \cdots a_{1})(a_{1}\cdot a_{-1})( a_{-1}\cdot a_{-1}\cdot \cdots a_{-1}) $ $= (a_{1}\cdot a_{1}\cdot \cdots a_{1})e( a_{-1}\cdot a_{-1}\cdot \cdots a_{-1}) $ $= \cdots = e$. Similarly, $a^{-n}a^{n} =e$. So, by uniqueness of inverses, $a^{-n} = (a^{-1})^n$. Also note that $\langle a\rangle = \langle a^{-1}\rangle$ because, $\forall m \in \mathbb Z, \langle a\rangle \ni a^m=(a^{-1})^m \in \langle a^{-n}\rangle$. We have that **prop**: $\langle a\rangle \vartriangleleft G$

- Important:
	- Let $G$ be a group and $H\vartriangleleft G$. By definition, this means that $H$ is a group in its own right so that:
		- $H$ has an indentity element, $e_H\in H$
		- $\forall a\in H$, then it has an inverse in $H$, say $a_H^{-1}\in H$, such that $aa_H^{-1}=a_H^{-1}a=e_H$
		- Then, $e_H=e=$(indentity in $G$) because, $\forall a\in H, since a\in G$ as $H\subset G$, we have $ae=ea=a$.
		- So, $e$ is an indentity in $H$, implying that $e=e^H$ by uniqueness of the indentity element.
		- Similarly, if $a^{-1}$ as the identity of $a\in G$, then $aa^{-1}=a^{-1}a=e=e_H$
		- $\Rightarrow a^{-1}$ is an indentity for $a\in H\Rightarrow a^{-1}=a_H^{-1}$ by uniqueness of inverse
	- **So**: if $H\vartriangleleft G$, then the indentity of $H$ is the indentity of G and the inverse of any element in $H$ is its inverse in $G$.
- Given a subset $H\subset G$, how can we tell if $H$ is $NOT$ a subgroup of $G$?
	- If $e\notin H$, then $H \not \vartriangleleft G$
	- If $H$ is not closed under the operation on $G$, then $H \not \vartriangleleft G$
		- E.g. $(G,\cdot) = (\mathbb R^*, \cdot)$ and $H = \{x\in(G, \cdot) \mid x=q or x \mathbb Q\}$. Note that $1\in H$, so that $H$ may be a subgroup of $G$. **BUT**, $\sqrt{2}\in H$ and $\sqrt{2}\sqrt{2} \notin H$
			- $\Rightarrow H$ is not closed under multiplication
			- $\Rightarrow H \not \vartriangleleft G$
	- $H$ is not closed under inverses, the $H \not \vartriangleleft G$ (i.e. If $\exists a \in G$ with $a^{-1} \notin H$, then $H \not \vartriangleleft G$)
		- E.g. $(G,\cdot) = (\mathbb R^*,\cdot)$ and $H = \{x\in (G,\cdot) \mid x\ge 1\}$. Note that $1\in H$. Also, $\forall x,y\in H, xy\in H$ because $xy \ge 1$ since $x,y\ge 1$. But, $2\in H$ and $2^{-1} = \frac{1}{2}\notin H$.
			- $\Rightarrow H$ is not closed under inverses
			- $\Rightarrow H\not \vartriangleleft G$
- Also not every of element in a group commute, some element commute with every element in a group. For example, if $G$ is a group, then $e$ commutes with every element in $G$ because $ae=ea, \forall a \in G$
- Definition (**Centre of a group**): Let $G$ be a group, we define $\mathcal Z(G):=\{a\in G\mid ax=xa, \forall x \in G\}$ = (element in $G$ that commute with all elements in $G$) = centre of G
	- Note: 
		- 1) $\mathcal Z$ is for zentrum = (centre in German)
		- 2) $e\in \mathcal Z(G)$
		- 3) If $G$ is abelian, then $\mathcal Z(G) = G$. In fact, we have ($G$ is abelian) $\Leftrightarrow$ ($\mathcal Z(G) = G$)
	- Ex: Consider $\mathcal G=GL(2,\mathbb R) = \{A\in M_{2\times 2}(\mathbb R)\mid \det A \neq 0\}$ under matrix multiplication. Let us show that $\mathcal Z(G) = \bigg \{\left.\begin{pmatrix}a&0\\0&a\end{pmatrix}\right\vert a\in R^*\bigg\}\subset \mathcal Z(G)$. Note that $\mathcal Z(G)\neq G$, which is to be expected since $G$ is not abelian!
	- Proof:
		- $\mathcal Z(G)\subset \bigg \{\left.\begin{pmatrix}a&0\\0&a\end{pmatrix}\right\vert a\in R^*\bigg\}\subset \mathcal Z(G)$
		- Let $\begin{pmatrix}a&b\\c&d\end{pmatrix}\in \mathcal Z(G)$ so that $\begin{pmatrix}a&b\\c&d\end{pmatrix}$ commutes with every matrix in $GL(2,\mathbb R)$
		- In particular:
			- $\begin{pmatrix}a&b\\c&d\end{pmatrix}\begin{pmatrix}1&0\\0&2\end{pmatrix}=\begin{pmatrix}1&0\\0&2\end{pmatrix}\begin{pmatrix}a&b\\c&d\end{pmatrix}$
				- $\Leftrightarrow \begin{pmatrix}a&2b\\c&2d\end{pmatrix}=\begin{pmatrix}a&b\\2c&2d\end{pmatrix}$
				- $\Rightarrow c = 2c$ and $2b = b$
				- $\Rightarrow c=b=0$
				- $\Rightarrow (a,0;0,b)$ (i.e. must be diagonal)
			- $\begin{pmatrix}a&0\\0&d\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}=\begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&0\\0&d\end{pmatrix}$
				- $ \Leftrightarrow \begin{pmatrix}a&a\\0&d\end{pmatrix}=\begin{pmatrix}a&d\\0&d\end{pmatrix}(a,a;0,d)=(a,d;0,d)$
				- $\Rightarrow a=d$
			- So $\mathcal Z(G) = {\begin{pmatrix}a&0\\0&a\end{pmatrix}\mid a\in R^*}$, where $a \neq 0$ because $\det \begin{pmatrix}a&0\\0&a\end{pmatrix} = a^2 \neq 0$
		- $\bigg \{\left.\begin{pmatrix}a&0\\0&a\end{pmatrix}\right\vert a\in R^*\bigg\}\subset \mathcal Z(G)$: 
			- Proof:
				- Consider $\begin{pmatrix}a&0\\0&a\end{pmatrix}$ with $a \in \mathbb R^*$. 
				- Then, $\forall \begin{pmatrix}x&y\\z&w\end{pmatrix}\in GL(2,\mathbb R)$, we have: $\begin{pmatrix}a&0\\0&a\end{pmatrix}\begin{pmatrix}x&y\\z&w\end{pmatrix}=\begin{pmatrix}ax&ay\\az&aw\end{pmatrix} = \begin{pmatrix}a&0\\0&a\end{pmatrix}$
				- $ \Rightarrow \begin{pmatrix}a&0\\0&a\end{pmatrix}\in \mathcal Z(G)$ 
				- and $\bigg \{\left.\begin{pmatrix}a&0\\0&a\end{pmatrix}\right\vert a\in R^*\bigg\}\subset \mathcal Z(G)$
- Theorem (**center is a subgroup**): Let $G$ be a group.Then $\mathcal Z(G) \vartriangleleft G$.
	- Proof:
		- Let us use 2-step subgroup test.
		- We need to verify that $\mathcal Z(G)$ is a) closed under the operation, and b) also closed under inverses. 
			- a) Let $a,b\in \mathcal Z(G)$. Then $ax=xa$ and $bx=xb, \forall x\in G$. Do we have $(ab)x = x(ab), \forall x \in G$?
				- Let $x\in G$. Then, $(ab)x = a(bx) = a(xb) = (ax)b = (xa)b = x(ab)$
				- $\Rightarrow ab\in \mathcal Z(G)$
			- b) Let $x\in \mathcal Z(G)$ so that $ax = xa, \forall x\in G$. Then $a^{-1}x = (x^{-1}a)^{-1} = (ax^{-1})^{-1} = (x^{-1})^{-1}a^{-1} = xa^{-1} \Rightarrow a^{-1}\in \mathcal Z(G)$

_2016/05/13_

- Review of last lecture:
	- Def: Let G be a group. Then $$\mathcal Z(G) = \{a\in G\mid ax=xa,\forall x\in G\} = center of G$$
		- Note: $G$ is abelian iff $\mathcal Z(G)=G$
- Theorem: $\mathcal Z(G)$ is a subgroup of $G$
- Definition (**Centraliser of an element $a$ in $G$**): Let $G$ be a group and $a \in G$. Then: $$\mathcal C(a):= {g\in G\mid ag=ga}\\=\{\text{set of all element in }G\text{ that commute with }a\}\\=\{\text{centraliser of }a\text{ in }G\}$$

- E.g.
	- 1) $\mathcal C(e) = G$ since, $\forall a\in G, eg=ge$
	- 2) If $a\in \mathcal Z(G)$, then $C(a)=G$. Moreover, if $a\in G$ is such that $\mathcal C(a)=G$, we must have that $a\in \mathcal Z(G)$, by definition of $\mathcal Z(G)$ So: $(a\in \mathcal Z(G))\Leftrightarrow(\mathcal C(a)=G)$
	- 3) $G=GL(2, \mathbb R)$. Then, $\mathcal Z(G) = \bigg \{\left.\begin{pmatrix}a&0\\0&a\end{pmatrix}\right.\mid a\in \mathbb R^* \bigg \}$
		- Consider $A=\begin{pmatrix}a&0\\0&b\end{pmatrix}$ with $a\neq b$ and $a,b\neq 0$ (so that $\begin{pmatrix}a&0\\0&b\end{pmatrix}\in G$)
		- Let us compute $\mathcal C(A)$. Note that since $A\notin \mathcal Z(G)$, we must have that $\mathcal C(A) \subsetneqq G$.
		- By definition, $\mathcal C(A)=\bigg \{\left.\begin{pmatrix}x&y\\z&w\end{pmatrix}\right.\in GL(2,\mathbb R)\mid A\begin{pmatrix}x&y\\z&w\end{pmatrix}=\begin{pmatrix}x&y\\z&w\end{pmatrix}A\bigg \}$
		- **BUT**, $\begin{pmatrix}a&0\\0&b\end{pmatrix}\begin{pmatrix}x&y\\z&w\end{pmatrix}=\begin{pmatrix}x&y\\z&w\end{pmatrix}\begin{pmatrix}a&0\\0&b\end{pmatrix} \Leftrightarrow \begin{pmatrix}ax&ay\\bz&bw\end{pmatrix}\Leftrightarrow ay=by$ and $bz=az \Leftrightarrow (a-b)y=0$ and $(a-b)z=0 \Leftrightarrow y=z=0$
		- So: $\mathcal C(A)=\bigg \{\left.\begin{pmatrix}x&0\\0&w\end{pmatrix}\right.\mid x,w\in \mathbb R^* \bigg \}\subset GL(2,\mathbb R)$
- Theorem: Let $G$ be a group and $a\in G$. Then, $\mathcal C(a)$ is a subgroup.
	- Proof: exercise
- Remark
	- 1) $\forall a\in G, \mathcal C(a)=\mathcal C(a^{-1})$
	- 2) $\mathcal Z(G) = \bigcap\limits_{a\in G} \mathcal C(a)$
	- Proof for exercise

## 1.3 Finite groups
- Definition: A group $G$ is called **finite** if $|G|<\infty$ (i.e. $G$ has a finite number of elements)
- E.g.:
	- 1) $(\mathbb Z_n, +) \leadsto |G|=n<\infty$
	- 2) $(\mathbb Z_n^*, \cdot) \leadsto |\mathbb Z_n^*|<|\mathbb Z_n|=n<\infty$
	- 3) **Permutations of degree $n$**
		- Permutations of degree $n$ is a bijection from $\{1,\cdots, n\}$ to itself, i.e. it is a map $$\sigma :{1,\cdots,n}\rightarrow{1,\cdots,n}$$ that is 1:1 and onto. The set of all permutation of degree n is denoted $S_n$
		- $S_n$ is group under the operation of composition $$S_n\times S_n \rightarrow S_n\\(\sigma, \tau)\mapsto\sigma\circ \tau$$ (which is well-defined because $\sigma,\tau:\{1,\cdots,n\}\rightarrow\{1,\cdots,n\}$ so that $\sigma\circ \tau$ is well-defined. and $\sigma\circ\tau$ is a bijection since $\sigma,\tau$ are both bijection) Also composition of function is associative, the identity permutation $id:\{1,\cdots,n\}\rightarrow\{1,\cdots,n\}, i\mapsto i$, is an identity for the operation of composition $\forall \tau\in S_n$, its inverse map $\tau^{-1}\in S_n$ and is an inverse for $\tau$ with respect to the operation of composition. So, $(S_n,\circ)$ is a group
			- Claim: $S_n$ has $n!$ elements
				- Proof: to determine $\sigma$, we just have to specify the values $\sigma_1, \cdots, \sigma_n$ which are **distinct**  element of $\{1,\cdots,n\}$ since $\sigma$ is 1:1
					- $\sigma(1)$ can take $n$ possible values since $\sigma(1)\in \{1,\cdots,n\}$
					- $\sigma(2)$ can take $n-1$ possible values once $\sigma(1)$ is fixed because $\sigma(2)\in \{1,\cdots,n\} \setminus \{\sigma(1)\}$
					- $\sigma(3)$ can take $n-2$ possible values once $\sigma(1)$ and $\sigma(2)$ is fixed because $\sigma(3)\in \{1,\cdots,n\} \setminus \{\sigma(1),\sigma(2)\}$
					- etc$\cdots$
					- $\sigma(n)$ can only take one possible value once $\sigma(1),...,\sigma(n-1)$ are fixed
					- Thus, there are $n(n-1)\cdots 1=n!$ possible ways of defining \sigma
		- So: $(S_n,\circ)$ is a finite group with $|S_n| = n!$, we often just write $S_n$ and call it the **symmetric group of degree n**.
- For a finite group $G$, checking that a subset $H\subset G$ is a subgroup is very simple
- Theorem (**Finite subgroup test**): Let $G$ be a finite group and let $\phi\ne H\subset G$. Then $$(H\text{ is a subgroup of }G)\Leftrightarrow(ab\in H, \forall a,b\in H)$$
	- Proof:
		- If $H$ is a subgroup of $G$, then it is closed under the operation in $G$ (by definition), so the property holds so that $ab\in H, \forall a,b\in H$. Since $H$ is closed under the operation in $G$, by the 2-step subgroup test, the only thing left is that $H$ is closed under inverse: $\forall a\in H, a^{-1}\in H$.
		- Let $a\in H$. If $a=e$, then $a^{-1}=e^{-1}=e=a\in H$. If $a\neq e$, consider the set $S={a, a^2, a^3, \cdots} = {a^m\mid m\in \mathbb N}$. Then $S\subset G$ with $G$ finite $\Rightarrow S$ has only a finite number of elements. 
		- Moreover, since $H$ is closed under the operation in $G$, we have that $$a^2=a\cdot a \in H\text{ since }a\in H\\a^3=a^2\cdot a\in H\text{ since }a,a^2\in H\\\text{etc}\cdots\\\Rightarrow a^m\in H, \forall m\in \mathbb N\\\Rightarrow S\subset H$$
		- Now, since $S$ is finite, $\exists i,j\in \mathbb N$ such that $i\neq j$ and $a^i=a^j$. Suppose that $i<j$ so that $j-i>0$ and so $j-i\in \mathbb N$.
		- Then, $a^{j-i}=e$ (since $a^i=a^j$) with $j-i\geq 1$ (since $j-i>0$)
			- If $j-i=1$, then $a=a^1=a^{j-i}=e$, which is impossible since we assumed that $a\neq e$
			- So, $j-i>1 \Rightarrow j-i-1>0$ and $j-i-1\in \mathbb N$
			- $\Rightarrow a^{j-i-1}\in S\subset H$
			- **BUT**, $a^{-1}=e\cdot a^{-1} = a^{j-1}\cdot a^{-1}=a^{j-i-1}\in H$

_2016/05/16_

- Review:
	- Definition: A group is **finite** if $|G|<\infty$
	- Theorem (**Finite subgroup test**): Let $G$ be a finite group and let $\phi\ne H\subset G$. Then $$(H\text{ is a subgroup of }G)\Leftrightarrow(ab\in H, \forall a,b\in H)$$
	- Note: For a finite group, it is enough to check whether a non-empty subset $H$ is closed under the operation to determine if $H$ is a subgroup.
- Ex:
	- Consider $\mathbb Z_n^*$, which is finite, and $k \in \mathbb N$ with $k|n$. Let $$H=\{\overline x\in \mathbb Z_n^*\mid x \bmod k=1\}$$
	- We need to check that this definition is independent of the representative $x$ of $\overline x$
	- [If $\overline{x'} = \overline x$, we need to check $$(x\bmod k =1)\Leftrightarrow(x'\bmod k =1)$$
	- But $\overline{x'} = \overline x$ in $\mathbb Z_n^*\Leftrightarrow x'+x+rn$ for some $r\in \mathbb Z$
	- However, $k|n$ so that $n=ks$ with $s\in \mathbb N$. Thus $$x'=x+rn=(x+rs)k$$
	- $\Rightarrow x'=x\bmod k$, and $$(x'\bmod k=1)\Rightarrow (x'+m'k=1)\text{ for some }m'\in \mathbb Z$$ $$\Leftrightarrow x+(rs)k+m'k=1$$ $$\Leftrightarrow x+k[rs+m']=1\text{ for some }m'\in \mathbb Z$$ $$\Leftrightarrow (x\bmod k=1)\text{ for some }m'\in \mathbb Z$$
	- $H=\{\overline x\in \mathbb Z_n^*\mid x\bmod k=1\}$
	- Here, the operation in $\mathbb Z_n^*$ is multiplication. If $\overline x, \overline y\in H$ so that $x\bmod k=1$ and $y\bmod k=1$, then $x+mk=1$ and $y+m'k=1$ for some $m,m'\in \mathbb Z$ and $$1=(x+mk)(y+m'k)=xy+[xm'+my+mm'k]k$$ $$\Leftrightarrow xy\bmod k=1\Rightarrow \overline{xy}\in H \Rightarrow \overline x\overline y \in H$$
	- So, by the finite subgroup test, $H$ is a subgroup of $\mathbb Z_n^*$ because $H\neq \emptyset$ (since $\overline 1\in H$ because $1\bmod k=1$)
- Defnition (**order of an element**): Let $G$ be a group. For any $a\in G$, the order of a is defined as the smallest _positive_ integer in such that $a^m=e$ (if it exists. If no such integer exists, then a is said to have **infinite order**. The order of a is denoted $|a|$.
	- Note:
		- 1) To compute the order of an element$a\in G$, consider the sequence of for for odeuts(?) $1^1,a^2,a^3\cdots,$ and the first power of a that is equal to $e$ will be the order of $a$
		- 2) $|e| = 1$ because $e^1=e$. In fact, if $a\in G$ with $|a|=1$, then $a^1=e$. So the only element in $G$ that has order $1$ is the identity $e$.
		- 3) $\forall a\in G, |a|=|a^{-1}|$
			- Proof: Suppose that $|a|=m$. Then, $a^m=e$. So, $$(a^{-1})^m=a^{-m}=(a^m)^{-1}=e^{-1}=e$$ So, by definition of the order of an element, since $(a^{-1})^m=e$, we have: $$|a^{-1}|\le m=|a|$$ One prove similarly that $|a|=|a^{-1}|\Rightarrow |a|=|a^{-1}|$
		- 4) $\forall a\in G, |\langle a\rangle|=|a|$ where $\langle a\rangle=\{a^r \mid r\in \mathbb Z\}$ (i.e., the number of element in $\langle a\rangle$ is equal to $|a|$)
			- Proof: exercise
		- 5) If $|G|<\infty$, then $|a|<\infty, \forall a\in G$, In fact, $|a|\le |G|$
			- Proof: exerciese
- E.x.
	- 1) $\mathbb Z_6=\{\overline 0, \overline 1, \overline 2, \overline 3, \overline 4, \overline 5\} \leadsto$ Here: operation is $+$ and $e=\overline 0$ Then: $$|\overline 0|=1$$ $$|\overline 1|=6\text{ because }\overline 1+\overline 1+\overline 1+\overline 1+\overline 1+\overline 1=\overline 6=\overline 6$$ $$\\overline 2|=3 \text{ because } \overline 2+\overline 2+\overline 2=\overline 6=\overline 0$$ $$|\overline 3|=2 \text{ because } \overline 3+ \overline 3=\overline 6 = \overline 0$$ $$|\overline 4|=3$$ $$|\overline 5|=6$$
		- Note that $$\overline 5^{-1}=\overline 1\text{ and }|\overline 5|=|\overline 1|=6,$$ $$\overline 4^{-1}=\overline 2\text{ and }|\overline 4|=|\overline 2|=3,$$ $$\overline 3^{-1}=\overline 3$$
	- 2) $\mathbb Z_6^* = \{\overline 1, \overline 5\}\leadsto$ Here: operation is $\cdot$ and $e=\overline 1$
		- $|\overline 1|=1, |\overline5|=2$ because $\overline 5\cdot \overline 5 = \overline 1$
	- 3) Not ever element of a group has finite order
		- e.g. $(G,\cdot)=(\mathbb Z, +)$. Then, $2\in \mathbb Z$ has infinite order because $2+2+\cdots+2=2m\neq0,\forall m\in \mathbb N$
- New example of a finite group: the **Dihedral group $D_n, n \ge 3$**. These groups represent symmetries of regular n-gons in $\mathbb R^2$
	- $n=3$: regular 3-gon is $\mathbb R^2$ is an equilateral triangle.
	- Consider the 6 following symmetries of the triangle (3 rotations+3 reflections):
		- $R_0=$ rotation about the origin by $0$ rad conterclockwise ![dihedrald3r0](http://www.maa.org/sites/default/files/images/cms_upload/d3sym436454.gif)
		- $R_1=$ rotation about the origin by $\frac{2\pi}{3}$ rad conterclockwise ![dihedrald3r1](http://www.maa.org/sites/default/files/images/cms_upload/d3sym537754.gif)
		- $R_2=$ rotation about the origin by $\frac{4\pi}{3}$ rad conterclockwise ![dihedrald3r2](http://www.maa.org/sites/default/files/images/cms_upload/d3sym638955.gif)
		- $H$: flip from height through point B in graph ![dihedrald3h](http://www.maa.org/sites/default/files/images/cms_upload/d3sym132371.gif)
		- $V$: flip from height through point A in graph![dihedrald3v](http://www.maa.org/sites/default/files/images/cms_upload/d3sym234053.gif)
		- $D$: flip from height through point C in graph![dihedrald3d](http://www.maa.org/sites/default/files/images/cms_upload/d3sym335250.gif)

_2016/05/18_

- Review:
	- $D_{n}=($ **dihedral group** $)=($group of symmetries of regular n-gon in $\mathbb R^2)$ (Here: rotations and reflections)
		- $R_0, R_1, R_2, H,V,D\cdots$
		- Set $D_3=\{R_0, R_1, R_2, H,V,D\}$
		- Claim: $D_3$ is a group under composition
		- First thing to check is that $D_3$ is closed under composition，i.e. $\forall f,g\in D_3, f\circ g\in D_3$
		- Table: 

    |$f\circ g$ |$ R_0 $|$ R_1 $|$ R_2 $|$ H  $|$ V  $|$ D  $|
    |---|---|---|---|---|---|---|
    |$R_0 $|$ R_0 $|$ R_1 $|$ R_2 $|$ H  $|$V  $|$ D  $|
    |$R_1 $|$ R_1 $|$ R_2 $|$ R_0 $|$ D  $|$ H$|$V$|
    |$R_2$|$R_2$|$R_0$|$R_1$|$V$|$D$|$H$|
    |$H$|$H$|$V$|$D$|$R_0$|$R_1$|$R_2$|
    |$V$|$V$|$H$|$D$|$R_2$|$R_0$|$R_1$|
    |$D$|$D$|$H$|$V$|$R_1$|$R_2$|$R_0$|

- 
   - 
      - Also:
			- composition is assotiation
			- $R_0$ is the identity
			- every element as an inverse: $R_0^{-1}=R_0, R_1^{-1}=R_2=R_2^{-1}=R_1, H^{-1}=H,V^{-1}=V,D^{-1}=D$
			- $\Rightarrow D_3$ is a group with 6 elements
		- In general, $D_{n}$ is a finite group with $|D_n|=2n$, where
			- $D_{n}$ will contain $n$ rotation (about the origin, counterclowise by $\frac{2\pi}{r}$ rad.) and $n$ reflections (read about in a textbook)
		- when $n=4$:
			- ![dihedral_d4](imgs/dihedral_d4.png)
			- $\Rightarrow$ only need to use either 2 vertices that are jointed by a diagonal OR $\frac{1}{2}$ point of 2 opposite edges to get all the reflections
			- $\Rightarrow$ since there are 4 vertices and 4 edges, get 4 reflections

# 1.4 Cyclic groups 
- Definition: A group G is called **cyclic** if $G=\langle a\rangle$ for some $a\in G$, where $$\langle a\rangle:=\{a^m\mid m\in \mathbb Z\}$$ (with $a_0=e$ and $a^{-m}=(a^m)^{-1}$). In this case, a is called a **generator of $G$**
- Ex:
	- 1) $(\mathbb Z,+)$. Then $\mathbb Z=\langle 1\rangle$ because, $\forall m\in \mathbb Z$,
		- if $m>0$: $m=1+1+\cdots+1$ ($m$ times) $= m(1)$
		- $0=0(1)$
		- if $m<0$: $m=-(-m)=-(1+\cdots+1)$ ($-m$ times)
		- Similarly, we see that $\mathbb Z=\langle -1\rangle$. We then see that generators are **not** unique.
		- Note: Here $\mathbb Z=\infty$ and $|1|=\infty$, which is a good thing! We will see that if $G=\langle a\rangle$, then $|G|=|a|$
	- 2) $(\mathbb Z_n,+)$. Then, $\mathbb Z_n=\langle \overline 1\rangle=\langle \overline{-1}\rangle=\langle \overline{n-1}\rangle$
		- $\leadsto \mathbb Z_n$ is a cyclic group it has at least 2 possible generators, usually, $\overline 1$ and $\overline{n-1}$ 
		- But, may have more than these two.
			- e.g. $\mathbb Z_8 = \langle \overline 1\rangle= \langle \overline 7\rangle= \langle \overline 3\rangle= \langle \overline 5\rangle$ because:
				- $\overline 3$
				- $\overline 3+\overline 3 = \overline 6$
				- $\overline 3+\overline 3 + \overline 3=\overline 9=\overline 1$
				- $\overline 3+\overline 3+\overline 3+\overline 3=\overline 4$
				- $\overline 3+\overline 3+\overline 3+\overline 3+\overline 3=\overline 7$
				- $\overline 3+\overline 3+\overline 3+\overline 3+\overline 3+\overline 3=\overline 2$
				- $\overline 3+\overline 3+\overline 3+\overline 3+\overline 3+\overline 3+\overline 3=\overline 5$ 
				- But, $\overline 2$ is not a generator since $$\langle \overline 2\rangle=\{\overline 0, \overline 2, \overline 4=\overline 2+\overline 2, \overline 6 = \overline 2+\overline 2+\overline 2\}\subsetneqq \mathbb Z_8$$
- Questions:
	- What is the order of a generator?
	- What are the possible generator?