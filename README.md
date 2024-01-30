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
 linear quadratic regulator (LQR), is formulated as stabilizing a time-invariant linear system to the origin. (https://underactuated.mit.edu/lqr.html)
