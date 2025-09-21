### Program 

- Linear program: everything is linear
- Quadratic program : quadratic objective function + linear constraints 
- Non-linear Program : the objective or at least one of the functions involves is not linear in x
- Combinatorial : the set of feasible solution is discrete-> (TSP,knapsack, graph...)

### variables

- Decision variables

- Auxiliary variables:

  Not fundamental to the problem, to help with the formulation (easier).

  Eg. minimize $\max_i f_i(x)$ => introduce constraints $f_i(x)\leq t$ 

- Slack variables

  Convert $\leq$ constraints into equalities (The unused capacity)

- Surplus variables

  Convert$\geq$ constraints into equalities(The extra amount)

- Artificial variables

  Introduced in the Big-M or Two-Phase simplex

- State variables

  Represent the state of the system at a given time step(inventory level?)

- Dual variables(Shadow prices)

  Arise in the dual problem or in KKT conditions

  Represent the marginal value of relaxing a constraint.

### Constraints

