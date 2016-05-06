**Important**: since github markdown don't support LaTeX, download the html file in repo instead!

--------------------------------------------------------------------------------

# Table of Content

- [Chapter 0: Course Administration](#toc_1) (May 02)
- [Chapter 1: Groups](#toc_2) (May 02)
    - [1.1 Definitions and examples](#toc_3) (May 02)
    - [1.2 Subgroups](#toc_4) (May 06)

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
    - The integers: $(\mathbb{Z},+) \rightsquigarrow $ this is a group
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
    - The integers: $(\mathbb{Z},\cdot)\rightsquigarrow$ this is a group
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
        - (iii) From the table, we see that $1$ is the inverse of $1$ and $-1$ is the inverse of $-1\rightsquigarrow$ every element in $G$ has an inverse.
- Ex 4)
    - $(\mathbb{Q}, +)$ is a group (exercise)
- Ex 5)
    -$ (\mathbb{Q}^*, \cdot)$ is a group where $\mathbb{Q}^* = \mathbb{Q}\setminus\{0\}$
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
	- Set $\mathbb{Z}_n^* = \{\text{units in }\mathbb{Z}_n\} = \{F\in \mathbb{Z}_n \mid gcd(r,n)=1\}$. Then, $(\mathbb{Z}_n*, \cdot)$ is a group
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
	- Theorem (**One-step subgroup test**): Let $H$ be a non-empty subset of a group $G$. If $ab^{-1}\in H,\forall a,b,\in H$, then $H\triangleleft G$