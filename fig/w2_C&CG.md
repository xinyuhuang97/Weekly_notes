## Background 

**Single-stage** RO models -> conservative facing uncertainty and perturrbation

**Two-stage** (multi-stage) RO model 

- **First stage**: Fix some variables (reveal uncertainty)
- **Second stage**: Model decision-making after the first-stage decisions are made
- **Application**: network/transportation problems, portfolio optimization, power system scheduling problems

**But** -> two-stage RO models are difficult to compute (could be NP-hard)

To overcome the computational burden:

- Use of **approximation algorithms**: assume the second-stage decisions are simple functions (e.g., affine functions)
- **Benders-dual cutting plane algorithms** -> gradually construct the value function of the first-stage decisions using dual solution of the second-stage decision problems