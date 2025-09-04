## Week 1 

### <u>Revision</u> 

**<u>Duality</u>**: In optimization, we consider a problem from two aspects. We have the primal problem and the dual problem.

Consider the primal problem a minimization problem($$\min c^Tx $$ , subject to $Ax\geq b,x\geq 0$), the dual problem a maximization problem($\max b^Ty$, subject to $A^Ty\leq c,y\geq0$).

**<u>Weak duality</u>** states that if $\bar{x}$ a feasible solution for the  primal problem and $\bar{y}$ a feasible solution for the dual problem, we have always

$$c^T\bar{x}\geq b^T\bar{y}$$ 

**<u>Strong duality</u>** is in contrast to weak duality, it states that in linear programming or under some conditions(Slater's condition) in convex optimization, the optimal solution for the primal problem and the dual problem is equal :

$$c^Tx^{\star}= b^Ty^{\star}$$ 

**<u>Slater's condition</u>**: there exist **points in the relative interior of the domain** in a convex optimization problem

$$minf_0(x)$$ subject to $f_i(x)\leq0$ and $Ax=b$ , with $f_0$ and $f_i$ convex. In such a problem, if there exists a point $x^{\star}$, which means $f_i(x)<0 \forall i$ Then we say that it satisfies Slater's condition, and strong duality holds.

**<u>Complementary slackness theorem</u>**: 

Conditions: 

$$(\sum_{j=1}^na_{ij}x_j-b_i)y_i=0$$

$$(c_j-\sum^m_{i=1}a_{ji} y_i)x_j=0$$ 

proof on https://personal.math.ubc.ca/~anstee/math340/340complementaryslackness.pdf

**Concretely** !! If a constraint of the primal is strictly satisfied(slack), which means the corresponding $$(\sum_{j=1}^na_{ij}x_j-b_i)>0$$ therefore $y_i=0$.

### <u>Notes</u> :

**<u>Lagrangian multiplier</u>** : 

​	Consider $\min f(x)$ subject to $g(x)=0$ It means that f(x) is forced to move along the surface created by the constraint g(x)=0. When f(x) attains its optimum in this case, it means that it's tangent point in the normal direction of that surface, which makes it "unable" to move.-> therefore they are parallel $\delta f(x^{\star})||\delta g(x^{\star})$, this can be expressed with a constant $\lambda$ : $\delta f(x^{\star}) + \lambda \delta g(x^{\star})=0$ . $\lambda$ is called the Lagrangian multiplier

Remark-> Lagrangian multiplier therefore, can help us transform the constrained problem into an equivalent unconstrained problem.

**<u>KTT</u>**:

​	We note $L(x,\lambda) = f(x)+\lambda g(x)$ , therefore we want to minimise $L(x,\lambda)$ .

The necessary condition for an optimal solution of $L(x,\lambda)$ is therefore:

- Stationary : $\delta_xL=\delta f+\lambda \delta g = 0$ 

- Primal feasibility : $\delta_{\lambda}L=g(x) = 0$

We can propagate this to the problem with inequality constraints :

$\min f(x)$ subject to $g_i(x) \leq 0$ , $h_j(x)=0$ , and we set $\mu$ and $\lambda$ their Lagrangian multiplier vectors.  We pose

$$L(x,\mu,\lambda)=f(x)+\mu^T g(x) +\lambda^T h(x)$$  

- Stationary equation: it is similar to the previous formulation, when f(x) with constraints attain its optimum, the tangent of f point not only in the normal direction of $h(x)$ , but also in the outward of g(x) ( The direction of increase of g(x), since the region is defined by g(x)<=0, then outward). Therefore, if there exist an optimum, we need to have:

  $$\delta_x L =\delta f +\mu^T\delta g(x)+\lambda^T\delta h(x) =0$$

- Primal feasibility: to respect constraints posed in the primal, we also need to have

  $$g_i(x)\leq0$$

  $$h(x)=0$$ 

- Dual feasibility:

  $\mu\geq0$ => why? in this case, the direction is not normal but with orientation, $\delta g(x)$ point outward, therefore, it requires $\delta f$ to point inward to satisfy the feasibility. 

  we have $\delta_x L =\delta f +\mu^T\delta g(x)+\lambda^T\delta h(x) =0$ 

  $\delta f =-\mu^T\delta g(x)-\lambda^T\delta h(x)$, $-\mu^T\delta g(x)$ force the objective function to point inward.

  From a duality pov, the dual problem is in fact $\max \min L(x,\mu,\lambda)$ , so if $\mu \leq 0$ , then as we know $g(x)\leq0$ , we have $\mu g(x)\geq 0$, which makes $L(x,\mu,\lambda)\geq f(x)$ , then the dual will not guarantee a valid lower bound.

- Complementary slackness

  $\mu^Tg(x^*)=0$ ,this is introduced before. 



Why do we want to know KKT? => KKT conditions are necessary for optimality in constrained optimization.

If $x^*$ is an optimal solution and under some regularity conditions, then there exists multipliers such that KKT condition holds.

Optimal solution + regularity conditions->KKT

If the problem is convex and the regularity condition holds -> the problem admits an optimal solution.



**C&CG** 

I know about this algorithm on the internet together with keywords like "robust optimization" and "KTT",





Remark 1: In no wonder convex or non-convex problem, the dual problem can always be used to provide bounds->the weak duality.

Remark 2: KKT + Slater< -> optimal solution <->strong duality

Remark 3: Lagrangian & KKT shows how to formulate the objective function of dual. 