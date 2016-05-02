# Chapter 0 Course Administration
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
    - **HERE**: G = $\mathbb{Z}$ and $\cdot: \mathbb{Z}\times\mathbb{Z} \rightarrow \mathbb{Z}, (m,n) \mapsto m\cdot n$
    - Does $\cdot$ satisfy properties (i) to (iii)?
        - (i) Let $m, n, r \in \mathbb{Z}$, then:
            - $m\cdot(n\cdot r) = (m\cdot n)\cdot r$ ? YES!
        - (ii) Identity of $\cdot$ is $1 \in \mathbb{Z}$
            - because $1 \cdot m = m \cdot 1 = m$, $\forall m \in \mathbb{Z}$
        - (iii) $\forall m \in \mathbb{Z}$, the inverse of m with respect to multiplication is $\frac{1}{m}$ (if $m \neq 0$), but $\frac{1}{m} \notin \mathbb{Z}$ if $m\neq\pm1$. So property (iii) fails!
        - Thus, $(\mathbb{Z},\cdot)$ is not a group.
- Ex 3)
    - G = {1, -1} set of 2 elements with the binary operation given by:

<table border="1">
  <tr>
    <td>$\cdot$</td>
    <td>1</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>1<br></td>
    <td>1</td>
    <td>-1</td>
  </tr>
  <tr>
    <td>-1</td>
    <td>-1</td>
    <td>1</td>
  </tr>
</table>

- (continue)
    - Note that $\cdot$ is just the usual product in $\mathbb{R}$ restricted to element in $G$. Then $G$ is a group because:
        - (i) $\cdot$ is associative because multiplication in $\mathbb{R}$ is associative
        - (ii) $1$ is the identity.
        - (iii) From the table, we see that $1$ is the inverse of $1$ and $-1$ is the inverse of $-1\rightsquigarrow$ every element in G has an inverse.
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
    - $({1, i, -1, -1}, \cdot)$ is a group, where $i \in \mathbb{C}$ such that $i^2 = -1$. Here:
<table border="1">
  <tr>
    <td>$\cdot$</td>
    <td>1</td>
    <td>i</td>
    <td>-1</td>
    <td>-i</td>
  </tr>
  <tr>
    <td>1<br></td>
    <td>1</td>
    <td>i</td>
    <td>-1<br></td>
    <td>-i<br></td>
  </tr>
  <tr>
    <td>i</td>
    <td>i</td>
    <td>-1</td>
    <td>-i</td>
    <td>1<br></td>
  </tr>
  <tr>
    <td>-1</td>
    <td>-1</td>
    <td>-i</td>
    <td>1</td>
    <td>i</td>
  </tr>
  <tr>
    <td>-i</td>
    <td>-i</td>
    <td>1</td>
    <td>i</td>
    <td>-1</td>
  </tr>
</table>


