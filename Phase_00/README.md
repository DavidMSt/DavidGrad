# Phase 0 — Mathematical Foundations

## Goal

Understand the mathematical and computational foundations required for modern machine learning systems.

Focus areas:
- gradients
- optimization
- computational graphs
- tensor operations
- dynamical systems prediction
- numerical implementation details

---

# Main Learning Task

Learn one-step dynamics prediction on a simple cyber-physical system.

Initial system:
- 1D mass-spring-damper system

Prediction task:

```text
[x_t, v_t, u_t] → [x_{t+1}, v_{t+1}]
```

where:
- x = position
- v = velocity
- u = external control force

---

# Tasks

## Python

- [ ] Generate synthetic trajectory data
- [ ] Implement Euler integration
- [ ] Plot trajectories
- [ ] Implement linear regression
- [ ] Implement gradient descent manually
- [ ] Predict next system state
- [ ] Compare prediction vs analytical solution

## C++

- [ ] Implement vector operations
- [ ] Implement dot product
- [ ] Implement matrix-vector multiplication
- [ ] Compare against NumPy outputs
- [ ] Measure runtime differences

---

# Notes

## Why a Mass-Spring-Damper System?

The system is:
- analytically tractable
- easy to simulate
- physically interpretable
- relevant to control and CPS
- simple enough for debugging

while still exposing:
- dynamics
- integration
- state evolution
- control inputs
- numerical errors

---

# References

- Control Systems lectures
- Numerical Optimization references
- Karpathy Micrograd
- TinyGrad
