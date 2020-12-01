# Physics-Informed Neural Network (PINN) for Solving Coupled PDEs Governing Thermochemical Physics in Bi-Material Systems
### Reference:
S. A. Niaki, E. Haghighat, X. Li, T. Campbell, and R. Vaziri, Physics-Informed Neural Network for Modelling the Thermo-Chemical Process in Composite-Tool Systems During Manufacture, arXiv preprint arXiv:2011.13511 (2020) https://arxiv.org/pdf/2011.13511.pdf

### Summary
This model solves the governing coupled system of differential equations -- including conductive heat transfer and resin cure kinetics -- by optimizing the parameters of a deep neural network using a physics-based loss function. To account for the vastly different behaviour of thermal conduction and resin cure,  PINN consisting of two disconnected subnetworks is designed, and a sequential training algorithm is developed that mitigates instability present in traditional training methods. An explicit discontinuities into the DNN at the composite-tool interface and enforce known physical behaviour directly in the loss function to improve the solution near the interface is incorporate . Finally, training of the PINN is performed with a technique that automatically adapts the weights on the loss terms corresponding to PDE, boundary, interface, and initial conditions. The performance of the proposed PINN is demonstrated in multiple scenarios with different material thicknesses and thermal boundary conditions in comparison to results from classical numerical methods, i.e. Finite Elemenet Method.
<br>
<br>
A composite-tool material system inside an autoclave undergoing an air temperature history during the processing time.<br>
<p align="center">
<img  align="center" src="https://github.com/saniaki/Sequential_PINN/blob/main/README_Images/Figure_01.png" width="500"/>
 </p>
<br>
<br>
Two separate networks are constructed for T and alpha with sequential training first on alpha, and then on T, until convergence. <br>
<p align="center">
<img  align="center" src="https://github.com/saniaki/Sequential_PINN/blob/main/README_Images/Figure_03.png" width="800"/>
</p>
<br>
<br>
A a discontinuous network architecture is utilized for the bi-material problem. Two separate networks T− and T+ are combined with Heaviside step function H to construct the solution space for T.<br>
<p align="center">
<img  align="center" src="https://github.com/saniaki/Sequential_PINN/blob/main/README_Images/Figure_04.png" width="800"/>
</p>
<br>
<br>
Four case studies are considered here: <br>
<p align="center">
<img  align="center" src="https://github.com/saniaki/Sequential_PINN/blob/main/README_Images/Case_Studies.png" width="400"/>
</p>
<br>
<br>
As an example, Temperature and degree of cure predictions from PINN and FEM for a 30mm composites on a 20mm tool with convective heat transfer at boundary (case study 2) is <br>
<p align="center">
<img  align="center" src="https://github.com/saniaki/Sequential_PINN/blob/main/README_Images/Figure_05.png" width="800"/> 
</p>
<br>
<br>
