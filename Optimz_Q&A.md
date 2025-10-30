- **1**.Why is the function
  $$
  f(x) = \max \{ f_1(x), f_2(x), \ldots, f_k(x) \}
  $$
  a convex function?

  **Answer** 

  #### 1. Direct proof (using the convexity definition)

  Let $f_i(x)$ be convex for each $i=1,\dots,k$.
   For any $x, y$ and $t\in[0,1]$:
  $$
  \begin{aligned}
  f(tx+(1-t)y)
  &=\max_i f_i(tx+(1-t)y) \\
  &\le \max_i \big(t f_i(x)+(1-t)f_i(y)\big) \\
  &\le t\max_i f_i(x)+(1-t)\max_i f_i(y) \\
  &= t f(x)+(1-t)f(y).
  \end{aligned}
  $$
  Thus, $f(x)$ satisfies the convexity inequality and is convex.

  #### 2. Epigraph proof

  The **epigraph** of $f$ is
  $$
  \operatorname{epi}(f)
  =\{(x,t)\mid t\ge f(x)\}
  =\bigcap_{i=1}^k \{(x,t)\mid t\ge f_i(x)\}
  =\bigcap_{i=1}^k \operatorname{epi}(f_i).
  $$
  Each $\operatorname{epi}(f_i)$ is convex since $f_i$ is convex.
   An intersection of convex sets is convex ⇒ $\operatorname{epi}(f)$ is convex ⇒ $f$ is convex.

- **2**Why is the function
  $$
  f(x)=\sum_{j=1}^{k}\alpha_j f_j(x),\quad \text{where } \alpha_j>0,\ j=1,\dots,k,
  $$
  a convex function?

  **Answer** 

  Assume each $f_j(x)$ is convex.
   For any $x,y$ and $t\in[0,1]$:
  $$
  \begin{aligned}
  f(tx+(1-t)y)
  &=\sum_{j=1}^{k}\alpha_j f_j(tx+(1-t)y) \\
  &\le \sum_{j=1}^{k}\alpha_j \big(tf_j(x)+(1-t)f_j(y)\big)
  \quad(\text{by convexity of each }f_j)\\
  &=t\sum_{j=1}^{k}\alpha_j f_j(x)+(1-t)\sum_{j=1}^{k}\alpha_j f_j(y)\\
  &=t f(x)+(1-t)f(y).
  \end{aligned}
  $$
  Hence $f(x)$ satisfies the convexity inequality ⇒ $f$ is convex.

- **3**If $g:\mathbb{R}^n\to \mathbb{R}$ is **concave** and $S=\{x: g(x)>0\}$, define
  $$
  f:S\to\mathbb{R},\qquad f(x)=\frac{1}{g(x)}.
  $$
  Show $f$ is **convex** on $S$.

  **Answer** One-line composition rule

  Let $\phi(t)=1/t$ on $(0,\infty)$. Then:

  - $\phi''(t)=2/t^3>0$ ⇒ $\phi$ is **convex**,
  - $\phi'(t)=-1/t^2<0$ ⇒ $\phi$ is **nonincreasing**.

  **Composition rule:** If $\phi$ is convex and **nonincreasing**, and $g$ is **concave**, then $\phi\circ g$ is **convex** on $\{g>0\}$.

  Hence $f=\phi\circ g$ is convex on $S$.

  ------

  ## Direct ε-free proof

  Fix $x,y\in S$ and $t\in[0,1]$. Concavity of $g$ gives
  $$
  g(tx+(1-t)y)\ \ge\ t\,g(x)+(1-t)\,g(y).
  $$
  Apply $\phi(t)=1/t$. Since $\phi$ is **decreasing**, the inequality **reverses**:
  $$
  \frac{1}{g(tx+(1-t)y)}\ \le\ \frac{1}{t\,g(x)+(1-t)\,g(y)}.
  $$
  Now use **Jensen** (or just convexity) of $\phi$ on $(0,\infty)$:
  $$
  \frac{1}{t\,g(x)+(1-t)\,g(y)}
  =\phi\big(t\,g(x)+(1-t)\,g(y)\big)
  \ \le\ t\,\phi(g(x))+(1-t)\,\phi(g(y))
  = t\,\frac{1}{g(x)}+(1-t)\,\frac{1}{g(y)}.
  $$
  Therefore,
  $$
  f(tx+(1-t)y)\ \le\ t f(x)+(1-t) f(y),
  $$
  so $f$ is convex on $S$.

- ### **4** Theorem (Composition: nondecreasing convex ∘ convex)

  Let $g:\mathbb{R}\to\mathbb{R}$ be **convex** and **nondecreasing**, and let $h:\mathbb{R}^n\to\mathbb{R}$ be **convex**.
   Define $f:\mathbb{R}^n\to\mathbb{R}$ by $f(x)=g(h(x))$. Then $f$ is **convex**.

  **Answer** 

  #### Proof (by definition of convexity)

  Take any $x,y\in\mathbb{R}^n$ and $t\in[0,1]$.
   Convexity of $h$ gives
  $$
  h(tx+(1-t)y)\ \le\ t\,h(x)+(1-t)\,h(y).
  $$
  Because $g$ is **nondecreasing**, applying $g$ preserves the inequality:
  $$
  g\!\big(h(tx+(1-t)y)\big)\ \le\ g\!\big(t\,h(x)+(1-t)\,h(y)\big).
  $$
  Now use **convexity** of $g$ (in one variable):
  $$
  g\!\big(t\,h(x)+(1-t)\,h(y)\big)\ \le\ t\,g(h(x))+(1-t)\,g(h(y)).
  $$
  Combine the two inequalities:
  $$
  f(tx+(1-t)y)\ \le\ t\,f(x)+(1-t)\,f(y).
  $$
  Thus $f$ is convex. ∎

  ------

  ### Smooth proof (Hessian test, if $g,h$ are $C^2$)

  If $g''\!\ge 0$ and $g'\!\ge 0$ (convex & nondecreasing), and $h$ is convex ($\nabla^2 h\succeq 0$), then
  $$
  \nabla^2 f(x) \;=\; g''(h(x))\,\nabla h(x)\nabla h(x)^\top \;+\; g'(h(x))\,\nabla^2 h(x)\ \succeq\ 0,
  $$
  a sum of PSD matrices, hence $f$ is convex.

  ------

  ### Notes & variants

  - If $g$ is **convex and nonincreasing**, then $g\circ h$ is convex when $h$ is **concave** (the first inequality flips).
  - If $g$ is convex but not monotone, $g\circ h$ need **not** be convex in general—monotonicity is essential here.

- ### Theorem

  Let $g:\mathbb{R}^m\to\mathbb{R}$ be convex and $h:\mathbb{R}^n\to\mathbb{R}^m$ be affine of the form $h(x)=Ax+b$. Then $f(x)=g(h(x))$ is convex on $\mathbb{R}^n$.

  ### Proof

  Take any $x,y\in\mathbb{R}^n$ and $t\in[0,1]$.
   Because $h$ is **affine**,
  $$
  h(tx+(1-t)y)=t\,h(x)+(1-t)\,h(y).
  $$
  By convexity of $g$,
  $$
  g\big(t\,h(x)+(1-t)\,h(y)\big)\le t\,g(h(x))+(1-t)\,g(h(y)).
  $$
  Combine the two displays:
  $$
  f(tx+(1-t)y)=g\big(h(tx+(1-t)y)\big)\le t\,f(x)+(1-t)\,f(y).
  $$
  Hence $f$ is convex. 

- 