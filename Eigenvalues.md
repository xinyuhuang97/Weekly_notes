### Invertible/ Singular

These two terms are opposite:

- Invertible<-> non singular & Singular<->non-invertible

**Invertible /Non-invertible** 

- $det(A)\neq0\quad/det(A)=0$ (As det(AA^-1)=1) 

- $rank(A)=n \quad rank(A)<n$ 

- Nullspace only {0}(Ax=0->x=0) / Nullspace contains a nonzero vector

- Columns are linearly independent/dependent

- Pivots in every row and column/missiong pivots

- 0 is not an eigenvalue/ is an

- Linear map is one-to-one and onto/ not one-to-one or not onto

  

## What is the **characteristic polynomial**?

For any square matrix $A$, the **characteristic polynomial** is defined as:
$$
p_A(\lambda) = \det(\lambda I - A)
$$
It’s a polynomial in $\lambda$, and its **roots** are exactly the **eigenvalues** of $A$.

------

### 💡 Why do we use it?

Because the **eigenvalue equation**
$$
A x = \lambda x
$$
can be rewritten as
$$
(A - \lambda I)x = 0.
$$
For this equation to have a **nonzero solution** $x \neq 0$, the matrix $(A - \lambda I)$ must be **singular** (i.e., not invertible).
 The condition for singularity is:
$$
\det(A - \lambda I) = 0.
$$
That determinant, as a function of $\lambda$, is the **characteristic polynomial** $p_A(\lambda)$.
 Solving $p_A(\lambda) = 0$ gives all eigenvalues.

------

## 🔹 Example 1: 2×2 matrix

Let
$$
A = \begin{pmatrix} 2 & 1 \\ 3 & 4 \end{pmatrix}.
$$
Compute:
$$
p_A(\lambda) = \det(\lambda I - A)
= \det\!\begin{pmatrix} \lambda - 2 & -1 \\ -3 & \lambda - 4 \end{pmatrix}
= (\lambda - 2)(\lambda - 4) - 3.
$$
Simplify:
$$
p_A(\lambda) = \lambda^2 - 6\lambda + 5.
$$
Then solve:
$$
\lambda^2 - 6\lambda + 5 = 0 \quad \Rightarrow \quad \lambda_1 = 1,\ \lambda_2 = 5.
$$
✅ **These two roots (1 and 5) are the eigenvalues** of $A$.

------

## 🔹 Example 2: 3×3 matrix (the one you showed)

$$
A = 
\begin{pmatrix}
0 & 2 & -2 \\
2 & 4 & 4 \\
-2 & 4 & -3
\end{pmatrix}.
$$

Compute the characteristic polynomial:
$$
p_A(\lambda) = \det(\lambda I - A)
= \det
\begin{pmatrix}
\lambda & -2 & 2 \\
-2 & \lambda - 4 & -4 \\
2 & -4 & \lambda + 3
\end{pmatrix}.
$$
After expanding this determinant:
$$
p_A(\lambda) = \lambda^3 - \lambda^2 - 36\lambda + 36.
$$
Factorizing:
$$
p_A(\lambda) = (\lambda - 6)(\lambda - 1)(\lambda + 6).
$$
✅ So, the eigenvalues are:
$$
\lambda_1 = 6,\quad \lambda_2 = 1,\quad \lambda_3 = -6.
$$

------

## 🔹 Why is this useful?

- The **eigenvalues** describe how the matrix stretches or flips space in certain directions.
- For example:
  - If all eigenvalues are positive → the matrix is positive definite.
  - If there are both positive and negative ones → the matrix is indefinite.
- The **trace** of $A$ = sum of eigenvalues.
- The **determinant** of $A$ = product of eigenvalues.
- The characteristic polynomial encodes all that information.

------

✅ **In summary:**

| Concept                              | Meaning                                          |
| ------------------------------------ | ------------------------------------------------ |
| $A x = \lambda x$                    | Eigenvalue definition                            |
| $(A - \lambda I)x = 0$               | Equivalent linear system                         |
| $\det(A - \lambda I) = 0$            | Condition for nonzero solution (singular matrix) |
| $p_A(\lambda) = \det(\lambda I - A)$ | Characteristic polynomial                        |
| Roots of $p_A(\lambda)$              | Eigenvalues                                      |