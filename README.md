# Physics-Informed Neural Networks for Solving Coupled First-Order PDEs

This repository presents an implementation of **Physics-Informed Neural Networks (PINNs)** for solving a coupled system of first-order partial differential equations representing three interacting temperature fields in a two-dimensional spatial domain. The PINN-based solution is rigorously validated against a classical **Finite Difference Method (FDM)** benchmark.

**Code will be released after manuscript publication.**  
**Manuscript is currently under final preparation.**

---

## Problem Overview

Physics-Informed Neural Networks embed governing physical laws directly into the loss function of neural networks, enabling mesh-free and physically consistent solutions to partial differential equations (PDEs).

This study focuses on:
- A **coupled system of first-order PDEs**
- Three interacting temperature fields
- A two-dimensional spatial domain

---

## Methodology

- **Neural Network Architecture**
  - Fully connected feedforward network
  - 4 hidden layers
  - 128 neurons per layer
  - Activation: `tanh`

- **Optimization Strategy**
  - Stage 1: Adam optimizer (rapid convergence)
  - Stage 2: L-BFGS quasi-Newton optimizer (solution refinement)

- **Loss Components**
  - PDE residual loss
  - Boundary condition loss
  - Initial condition loss

---

## Validation & Evaluation

The PINN solution is validated against a Finite Difference Method (FDM) reference using:

- Pointwise error analysis
- Global relative error metrics
- PDE residual evaluation
- Boundary and initial condition enforcement

### Key Results:
- **Average relative error:** ~0.30%
- **Maximum local error:** < 1%
- **Mean PDE residual:** ~0.015
- **Maximum residual:** ~0.54
- **Boundary condition MAE:** < 0.0012
- **Final training loss:** ~0.003
- **Training time:** ~12–13 minutes (GPU)
- **Loss reduction:** ~10 orders of magnitude

---

##  PINNs vs FDM

| Aspect | PINNs | Finite Difference Method |
|------|------|-------------------------|
| Mesh requirement | ❌ No | ✅ Yes |
| Solution form | Continuous | Discrete |
| Multi-physics coupling | Excellent | Complex |
| Computational speed | Slower | Faster |
| Flexibility | High | Limited |

---

## Code Availability
**Source code will be made publicly available after paper acceptance and publication.**

---

## Manuscript Status
**Manuscript:** Under final preparation  

---

