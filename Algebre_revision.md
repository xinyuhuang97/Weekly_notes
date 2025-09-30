**Rank–nullity:** $\dim V=rank(T)+\dim(\ker T)$.

$kerA=\{x:Ax=0\}.$=> non space

Rank(T), the dimension of the image of a linear map T:V->W



#### Sub-space dimension formula 

#### Question why $det(M)=0$ mean that the matrix is non-invertible?

$$det(MM^{-1})=det(I)=1=det(M)det(M^-1)$$

Therefore is $det(M)=0$ This equivalent doesn't hold anymore.



#### Spectral Theorem

Let $A\in \mathbb{R}^{m\times n}$ be a symmetric matrix (with distinct eigenvalues) $\lambda_1,\cdots,\lambda_n$ , then there exists an orthogonal matrix $Q$ such that 



$$Q^\top A Q =
\begin{pmatrix}
\lambda_1 & 0        & \cdots & 0        & 0 \\
0         & \lambda_2& \cdots & 0        & 0 \\
\vdots    & \vdots   & \ddots & \vdots   & \vdots \\
0         & 0        & \cdots & \lambda_{n-1} & 0 \\
0         & 0        & \cdots & 0        & \lambda_n
\end{pmatrix}$$

where $\lambda_1,\lambda_2,\cdots,\lambda_n$ are the (real) eigenvalues of matrix A.

**Proof by induction** 

An orthogonal matrix :


$$
\left(
\begin{array}{c}
Q_1^\top\\
Q_2^\top\\
\vdots\\
Q_{n-1}^\top\\
Q_n^\top
\end{array}
\right)
\left(
\begin{array}{c|c|c|c|c}
Q_1 & Q_2 & \cdots & Q_{n-1} & Q_n
\end{array}
\right)
$$


**Hermitian matrix** 

A complex square matix eauls to it's own conjugate-transpose:

$$A=A^{\star}\quad (A^{\star}=\bar{A}^T)$$ 

Over $\mathbb{R}$, reduce to symmetric $A=A^T$ 

**Rayleigh quotient** of a nonzero vector x for a (real symmetric/complex Hermitian) matrix $A$ is :

$$R_A(x)=\frac{x^TAx}{x^Tx} \quad (or x^{\star}Ax/x^{\star}x \text{ in complex})$$

->"average eigenvalue" seen by x

**Properties** 

Let $\lambda_{min}\leq \cdots\leq \lambda_{max}$ be eigenvalues of $A$ 

1. Bounds and extrema

   $\lambda_{min}\leq R_A(x)\leq \lambda_{max} \quad \forall x\neq 0$ 

2. Stationary points = eigenvectors

   Setting $||x||=1$. Using langrange multipliers on $f(x)=x^TAx$ with $g(x)=x^Tx-1$

   $$\nabla f = 2Ax =\lambda\nabla g =2\lambda x=>Ax=\lambda x$$

   So critical points of $R_A$ are eigenvectors.

3. Spectral decomposition view

   If $A=Q\Lambda Q^T$ and $x=\sum_i \alpha_i q_i$(ONB of eigenvectors), then  with $||x||^2=\sum_i\alpha^2_i$ 

   $$R_A(x)=\frac{\sum_i\lambda_i \alpha_i^2}{\sum_i \alpha^2_i}$$ 

   a convex combination of eigenvalues.

**Spectral Theorem (real symmetric)**
 If $A\in\mathbb{R}^{n\times n}$ is symmetric ($A^\top=A$), then there exists an orthogonal matrix $Q$ and a real diagonal matrix $\Lambda=diag(\lambda_1,\dots,\lambda_n)$ such that


$$
Q^\top A Q=\Lambda.
$$


Equivalently, $A$ has an orthonormal basis of eigenvectors.

**Proof (by induction on $n$).**

**Base $n=1$.** Trivial.

**Inductive step.** Assume the claim holds for $(n-1)\times(n-1)$. Let $A\in\mathbb{R}^{n\times n}$ be symmetric.

1. **Existence of a real eigenpair (Rayleigh–Ritz).**
    Consider the Rayleigh quotient on the unit sphere:
   $$
   R(x)=\frac{x^\top A x}{x^\top x},\quad \|x\|=1.
   $$
   The sphere is compact and $R$ is continuous, so a maximizer $v$ exists with $\|v\|=1$. Using Lagrange multipliers for
   $$
   \max x^\top A x\quad\text{s.t.}\quad x^\top x=1,
   $$
   gives
   $$
   \nabla(x^\top A x)=\lambda\,\nabla(x^\top x)\ \Longrightarrow\ 2Ax=2\lambda x
   \ \Longrightarrow\ Av=\lambda v.
   $$
   Thus $v$ is an eigenvector and $\lambda=R(v)\in\mathbb{R}$.

2. **Orthogonal complement is invariant.**
    Let $W:=v^\perp=\{w\in\mathbb{R}^n:\ v^\top w=0\}$. For any $w\in W$,
   $$
   v^\top(Aw)=(A^\top v)^\top w=(Av)^\top w=(\lambda v)^\top w=\lambda\,v^\top w=0,
   $$
   hence $Aw\in W$. So $A$ restricts to a symmetric linear map $A|_W:W\to W$ with $\dim W=n-1$.

3. **Diagonalize on $W$ by induction.**
    By the induction hypothesis, there is an **orthonormal** eigenbasis $\{u_2,\dots,u_n\}\subset W$ with
   $$
   A u_i=\mu_i u_i\quad (i=2,\dots,n).
   $$

4. **Assemble an orthonormal eigenbasis of $\mathbb{R}^n$.**
    Set $u_1:=v$. Then $\{u_1,\dots,u_n\}$ is orthonormal, and
   $$
   Au_1=\lambda u_1,\qquad Au_i=\mu_i u_i\ (i=2,\dots,n).
   $$
   Let $Q=[\,u_1\ \cdots\ u_n\,]$. Since the columns are orthonormal, $Q^\top Q=I$, and
   $$
   Q^\top A Q=\operatorname{diag}(\lambda,\mu_2,\dots,\mu_n).
   $$
   This completes the induction. $\square$ 

   



**Sylvester's criterion**  

For a real symmetric matrix $A$ 

- A is possitive definite (PD) iff all leading principal minor are strictly positive
- $A$ is positive semidefinite(PSD) iff all principal minors(not just leading ones) are nonnegative

### What are leading principal minors?

For an $n \times n$ matrix:

- The **1st leading principal minor** is the determinant of the upper-left $1\times 1$ block.
- The **2nd leading principal minor** is the determinant of the upper-left $2\times 2$ block.
- … and so on up to the full matrix.

For example, for
$$
A = \begin{pmatrix}
a & c \\
c & b
\end{pmatrix},
$$

- The **first leading principal minor** is just $a$.
- The **second leading principal minor** is $\det(A) = ab - c^2$.

So the PSD conditions come directly from requiring:
$$
a \geq 0, \quad ab - c^2 \geq 0.
$$
For PD instead, you’d require:
$$
a > 0, \quad ab - c^2 > 0.
$$

## Convex optimization

Given $S \subseteq \mathbb{R}$

**Minumum/maximum**

a is the minimum of $S$ if 

- $a \in S$ 
- $a\leq s\quad \forall s\in S$

**Infimum/suppremum** 

Define $T=\{t\in \mathbb{R}|t\leq s \quad \forall s \in S\}$

- If $T=\empty$, we say that the infimum of $S$ is $-\infty$ 
- If $T\neq \empty$, we say that $a$ is the infimum of $S$ 
  - $a\in T$ 
  - $a \geq t \quad \forall t \in T$    

**Neighbourhood** 

$\forall x\in \mathbb{R}^n,\forall \epsilon \geq 0$

$$N_{\epsilon}(x)=\{y\in\mathbb{R}^n||y-x|\leq\epsilon\}$$

is a $\epsilon$-neighbourhood of x.

**Closure**

$S$ an arbitrary set in $\mathbb{R}^n$ 

- A point x is in the **closure** of S $cl(S)$, denoted by cl(S), if 

  $$S \cap \N_{\epsilon}(x)\neq \empty, \forall \epsilon>0$$

- if closed if $S=cl(S)$ 

**Interior** 

$int(S)$, a point $x$ is in the interior of $S$, if 

- $\exist\epsilon \geq0 \quad N_{{\epsilon}}(x) \subset S$
- if open if $S=int(S)$

**Boundary**

A point $x$ is on the boundary  of $S,\quad \partial(S)$ if 

$ S \cap N_{{\epsilon}}(x)\neq \empty$ and $\bar{S} \cap N_{\epsilon}(x)\neq \empty \quad \forall \epsilon>0$

- Possible that the boundary of S contains no elements of S

**Theoreme** 

A set $S \subseteq R^n$ is closed iid for any convergent sequence of points $\{x_j\}^{\infty}_{k=1}$ contained in S then 

Some rules

- S is closed iff $\partial{{S}} \subseteq S$

- S is open iff $\partial(S)\subseteq \bar{S}$

- S can be neither closed nor open.

- If $x\in S$, then $x\in int(S)$ or $x\in \partial(S)$ 

- A set $S$ is bounded if there exist $\epsilon \ge 0$ and $x\in \mathbb{R}^n$such that 

  $$S \subseteq N_{\epsilon}(x)$$

- A set $S$ is compact if S both bounded and closed



### Weiestrass Theorem 

Let $S$ be a subset of $\mathbb{R}^n$ which is closed and bounded. Let $f:S->\mathbb{R}$ a continuous function on S. Then the problem $\min{f(x), x\in S}$ attains its minimum.



**Polyhedron** 

**Cone** 

**Convex cone**

Let $C$ be a cone. Then $C$ is convex iif $x+y\in C \quad \forall x,y \in C$

**Convex hull/envelope convex** 

- The convex hull is the smallest convex set containning S

Convex combination

Affine combination (drop the nonnegativity)

Linear combination(drop the nonnegativity and sum equals to 1)

Conic combination (drop the sum equals to 1)

! conic hull is the smallest convex cone containing S.

**Polytope** 

The convex hull of a finite number of points in $S={x^{(1)},\cdots, x^{(k)}}$ is called a polytope

Polytope is polyhedron 

Polyhedron not necessarily polytope ->unbounded polyhedron

**Linear independent** 

**Affine independent** 

**Carathéodory's Theorem**

Let $S \subseteq \mathbb{R}^n$ . Then $\forall x \in con(S)$, There exists $x_1,x_2\cdots,x_p$, where $p\leq n+1$ such that $x\in con{x_1,\cdots x_p}$









 

 

 