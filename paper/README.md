## Research Paper Information

Title
-----
Physics-Informed Neural Networks for Solving Coupled Systems of First-Order Partial Differential Equations


Authors
-------
Aadarsh S Nair


Abstract
--------
Physics-Informed Neural Networks (PINNs) have emerged as a promising alternative to conventional numerical solvers for partial differential equations by embedding governing physical laws directly into the learning framework. This study investigates the application of PINNs for solving a coupled system of first-order partial differential equations representing three interacting temperature fields in a two-dimensional spatial domain.

A fully connected neural network with four hidden layers and 128 neurons per layer is trained using a two-stage optimization strategy that combines the Adam optimizer for rapid convergence and the L-BFGS quasi-Newton method for solution refinement. The PINN solution is rigorously validated against a classical Finite Difference Method (FDM) benchmark through pointwise error analysis, global relative error metrics, PDE residual evaluation, and boundary condition enforcement.

The results demonstrate strong agreement between the two approaches, with an average relative error of approximately 0.30 percent and maximum local errors below 1 percent. The governing equations are satisfied with bounded residuals, exhibiting a maximum value of 0.54 and a mean magnitude of 0.015, while boundary and initial conditions are enforced with a mean absolute error below 0.0012. Training convergence analysis shows that the combined optimization strategy reduces the total loss by nearly ten orders of magnitude, reaching a final value of 0.003 after 20,000 epochs.

Although the Finite Difference Method remains computationally faster for this problem, the PINN framework offers significant advantages, including mesh-free computation, continuous solution representation, and enhanced flexibility for complex coupled multi-physics systems.


Status
------
Under final prepration


Note
----
The complete manuscript, experimental source code, trained models, and reference numerical solutions will be made publicly available upon publication.
