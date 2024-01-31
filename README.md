# StateObserversandRegulators

# Terminology
A state observer or state estimator is a system that provides an estimate of the internal state of a given real system, from measurements of the input and output of the real system.
Some observer structures: Linear, delayed, sliding mode, high gain, Tau, homogeneity-based, extended and cubic observers
If a system is observable,  then the output of the plant, y can be used to steer the state of the state observer.

# Luenberger observer

```math
x_{k+1}  = Ax_{k} + Bu_k
```
```math
\hat{x}_{k+1}  = A\hat{x}_{k} + Bu_k +L(y_k-\hat{y}_k)
```
Subtract them in order and define $e_{k} = x_{k} - \hat{x}_{k}$

```math
{e}_{k+1}  = Ae_{k} - L(y_k-\hat{y}_k)
```
Also define  $y_{k} = Cx_{k}$  to get
```math
{e}_{k+1}  = Ae_{k} - L(Cx_{k}-C\hat{x}_k)
```
Finally we get
```math
{e}_{k+1}  = Ae_{k} - LCe_{k}
```

```math
{e}_{k+1}  = (A-LC)e_{k}
```

 The Luenberger observer for this discrete-time system is therefore asymptotically stable when the matrix A − L C {\displaystyle A-LC} has all the eigenvalues inside the unit circle

 # LQR
The case where the system dynamics are described by a set of **linear** differential equations and the cost is described by a **quadratic** function is called the **LQ** problem.
Linear–quadratic regulator (LQR) is a feedback controller whose equations are to be given below. 

LQ-regulator design assumed that all the state variables are available for feedback. In practice, not all state variables are measured.
The assumption is that we know the system description
(A, B, C) and that (A, C) is observable


linear quadratic regulator (LQR), is formulated as stabilizing a time-invariant linear system to the origin.[1]

Note: If the state equation is quadratic then the problem is known as the quadratic-quadratic regulator (**QQR**). The Al'Brekht algorithm can be applied to reduce this problem to one that can be solved efficiently using tensor based linear solvers.
If the state equation is polynomial then the problem is known as the polynomial-quadratic regulator (PQR). Again, the Al'Brekht algorithm can be applied to reduce this problem to a large linear one which can be solved with a generalization of the Bartels-Stewart algorithm; this is feasible provided that the degree of the polynomial is not too high.

Model predictive control and linear-quadratic regulators are two types of optimal control methods that have distinct approaches for setting the optimization costs. In particular, when the LQR is run repeatedly with a receding horizon, it becomes a form of model predictive control (MPC). In general, however, MPC does not rely on any assumptions regarding linearity of the system.[2]

# MATLAB part
Although Bryson's rule usually provides satisfactory results, it is often just the **starting point of a trial-and-error iterative design procedure** to tune your closed-loop system response based on the design requirements.[3]

## Source List
[1] https://underactuated.mit.edu/lqr.html
[2] https://en.wikipedia.org/wiki/Linear%E2%80%93quadratic_regulator
[3] https://www.mathworks.com/help/control/ref/lti.lqr.html
