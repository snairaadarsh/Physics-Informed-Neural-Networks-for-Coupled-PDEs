# Physics-Informed Neural Networks for Solving Coupled First-Order PDEs

This repository presents an implementation of Physics-Informed Neural Networks (PINNs) for solving a coupled system of first-order partial differential equations representing three interacting temperature fields in a two-dimensional spatial domain. The PINN-based solution is rigorously validated against a classical Finite Difference Method (FDM) benchmark.

Code will be released after manuscript publication.
Manuscript is currently under final preparation.


Problem Overview
----------------
Physics-Informed Neural Networks embed governing physical laws directly into the loss function of neural networks, enabling mesh-free and physically consistent solutions to partial differential equations.

This study focuses on:
- A coupled system of first-order PDEs
- Three interacting temperature fields
- A two-dimensional spatial domain


Governing Equations
-------------------
The physical system is modeled using the following coupled first-order partial differential equations:

Equation (1):
dT1/dx = R1 * (T - T1)

Equation (2):
dT/dy = R2 * (T1 - T) + R3 * (T2 - T)

Equation (3):
dT2/dx = R4 * (T - T2)

Here, R1, R2, R3, and R4 are coupling coefficients that govern the interaction strength between the temperature fields.


Methodology
-----------
Neural Network Architecture
- Fully connected feedforward neural network
- Four hidden layers
- 128 neurons per layer
- Activation function: tanh

Optimization Strategy
- Stage 1: Adam optimizer for rapid convergence
- Stage 2: L-BFGS quasi-Newton optimizer for solution refinement

Loss Components
- PDE residual loss
- Boundary condition loss
- Initial condition loss


Validation and Evaluation
-------------------------
The PINN solution is validated against a Finite Difference Method reference using:
- Pointwise error analysis
- Global relative error metrics
- PDE residual evaluation
- Boundary and initial condition enforcement


Key Results
-----------
- Average relative error approximately 0.30 percent
- Maximum local error below 1 percent
- Mean PDE residual approximately 0.015
- Maximum PDE residual approximately 0.54
- Boundary condition mean absolute error below 0.0012
- Final training loss approximately 0.003
- Training time approximately 12 to 13 minutes on GPU
- Loss reduction of nearly ten orders of magnitude


PINNs vs FDM
------------
Aspect: Mesh requirement
PINNs: No
FDM: Yes

Aspect: Solution form
PINNs: Continuous
FDM: Discrete

Aspect: Multi-physics coupling
PINNs: Excellent
FDM: Complex

Aspect: Computational speed
PINNs: Slower
FDM: Faster

Aspect: Flexibility
PINNs: High
FDM: Limited


Code Availability
-----------------
Source code will be made publicly available after paper acceptance and publication.


Manuscript Status
-----------------
Under final preparation
