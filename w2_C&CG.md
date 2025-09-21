## Background 

**Single-stage** RO models -> conservative facing uncertainty and perturrbation

**Two-stage** (multi-stage) RO model 

- **First stage**: Fix some variables (reveal uncertainty)
- **Second stage**: Model decision-making after the first-stage decisions are made
- **Application**: network/transportation problems, portfolio optimization, power system scheduling problems

**But** -> two-stage RO models are difficult to compute (could be NP-hard)

To overcome the computational burden:

- Use of **approximation algorithms**: assume the second-stage decisions are simple functions (e.g., affine functions)
- **Benders-dual cutting plane algorithms** -> gradually construct the value function of the first-stage decisions using dual solution of the second-stage decision problems$\sigma$

## Two-stage RO

#### Assumption 

- Linearity: first- and second-stage problems are **linear** optimization models
- The uncertainty should be a **discrete set** or a **polyhedron** 

#### Formulation

- $y$ first-stage decision variable
- $x$ second-stage decision variable
- $U$ the uncertainty set (discrete set/polyhedron)
- $S_y$, $S_x$  basic feasible sets of variables $y$ and $x$ 
  - $S_y$ all admissible $y$ before we impose coupling constraints $Ay\geq d$ 
  - $S_x$ all admissible $x$ before we impose coupling constraints involving $x$ and $y$ 
- $F(y,u)$ feasible region for $x$ once $y$ (First stage variables) and $u$  (uncertainty or senario) are fixed

$$\min_y c^ty +\max_{u\in U} \min_{x\in F(y,u)}b^Tx$$ 

$$s.t. Ay\geq d, y\in S_y$$

Where $F(y,u) =\{x\in S_x: G_x \geq h -Ey-M\mu\}$ 

- $Gx$ constraint matrix on $x$
- $h-Ey-Mu$ RHS depending on $y$ and $u$ 

#### Bender-decomposition method 

Also denoted as **Benders-dual methods** 

#### Assumption 

- **Linearity**: second-stage problem is a linear programming problem in $x$ 
- ***Relatively complete recourse*** assumption: this LP is feasible for any given $y$ and $u$ 

#### Incomplete formulation 

- $\pi$ dual variables

The **dual problem** is a maximization problem:(subproblem in the Benders-dual method)

$$\text{SP}\max_{u,\pi}\{(h-Ey-Mu)^T\pi:G^T\pi\leq b, u\in U, \pi \geq 0\}$$ 

Assume thattm for given $y_k^*$ , an optimal solution $(u^{\star}_k ,\pi^{\star}_k)$ that solves $Q(y^*_k)$ can be obtained by a solution oracle. A cutting plane can be generated :

$$\eta\geq(h-Ey-Mu^{\star}_k)^T\pi^{\star}_k$$  

And we can introduce it into the master problem:

$$\text{MP}\min_{y, \eta} c^Ty+\eta$$

$$s.t. Ay\geq d$$

$$\eta \geq (h-Ey-Mu^{\star}_i)\pi^{\star}_i, \quad \forall l \leq k$$

$$y \in S_y, \eta \in R$$

We can coumpte an optimal solution $(y^{\star}_{k+1},\eta^{\star}_{k+1})$ in this case. Since we know that the dual program provides the upper bound and the promal program provides the lower bound, then  we have

- Upper bound: $c^Ty^{\star}_{k+1}+Q(y^{\star}_k)$ 
- Lower bound: $c^Ty^{\star}_{k+1} +\eta^{\star}_{k+1}$ 

Therefore, by iteratively introducing cutting planes and computing $\text{MP}$, an optimal solution can be obtained.

#### Complexity 

The complexity of the Benders-dual algorithm is $O(pq)$ iterations 

- $p$ number of extreme points of $U$ 
- $q$ number of extreme points of $\{\pi: G^T\pi \leq b, \pi\geq0\}$

This cut is called **optimality cut** 

! When the relatively complete resourse assuption does not hold-> *feasibility cut* 

## CCG 

#### Assumption

- $U$ is a finite discrete set

Then the two-stage RO:

