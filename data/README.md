## Methodology and Experiment Details

Data Sampling Strategy
----------------------
Collocation points within the interior of the computational domain are sampled to enforce the governing physical laws during PINN training. Since no labeled solution data is required, these points are used to minimize the residuals of the governing partial differential equations.

A hybrid sampling strategy is employed, combining uniform random sampling across the entire domain with biased sampling in regions exhibiting stronger spatial variation. Uniform sampling ensures global domain coverage, while biased sampling increases point density in regions with higher gradients or stronger coupling effects. This improves solution accuracy without significantly increasing computational cost.

Boundary and initial condition points are sampled separately to ensure accurate enforcement of the prescribed physical constraints.


Governing Equations
-------------------
The physical system is modeled using a coupled system of first-order partial differential equations representing three interacting temperature fields: T, T1, and T2.

Equation (1):
dT1/dx = R1 * (T - T1)

Equation (2):
dT/dy = R2 * (T1 - T) + R3 * (T2 - T)

Equation (3):
dT2/dx = R4 * (T - T2)

Here, R1, R2, R3, and R4 are coupling coefficients governing the interaction strength between the temperature fields.


Role in PINN Training
---------------------
During training, the neural network predicts the temperature fields as continuous functions of the spatial coordinates. Automatic differentiation is used to compute the required spatial derivatives.

The residuals of the governing equations are directly incorporated into the loss function, ensuring that the learned solution satisfies the underlying physical laws throughout the domain. This enables a mesh-free, continuous approximation of the coupled temperature fields.
