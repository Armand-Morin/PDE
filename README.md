# PDE mini-project Armand MORIN
# Modeling of a flow in a tube with presence of cylinder


The project consists of studying the flow of a fluid (water, but it can also be oil in a cylinder or another fluid) in a pipe containing a cylinder. This modeling is therefore based on the study of the Navier Stokes equations.
We consider the general incompressible Navier-Stokes equations on a domain <img src="https://latex.codecogs.com/svg.latex?\Omega%20\subset%20\mathbb{R}%20^2" />, consisting of a pair of equations where u corresponds to the velocity of the fluid and p to the pressure:

<img src="https://latex.codecogs.com/svg.latex?\begin{cases}\rho\frac{\partial%20u}{\partial%20t}%20%20+%20u%20\nabla%20u%20-%20\nu\Delta%20%20u%20+%20\nabla%20p%20=%200%20%20\\\nabla%20u%20=0%20\\\end{cases}" /> 
 
 
With the parameter <img src="https://latex.codecogs.com/svg.latex?\nu"/> is the dynamic viscosity.

This problem combines several challenges because in the equations we have a time dependence of more they are nonlinear and the variables are vector values. In addition there are two unknowns that we are looking for: speed and pressure.

In our case, the model can be rewritten as follows:

<img src="https://latex.codecogs.com/svg.latex?\begin{cases}\rho(\frac{\partial%20u}{\partial%20t}%20%20+%20(u%20\cdot%20\nabla)%20u)%20=%20\nu\nabla%20%20\sigma(u,p)%20+%20f%20%20%20\\\nabla%20u%20=0%20\\\end{cases}" />

On the right side f is a given force expressed per unit volume, <img src="https://latex.codecogs.com/svg.latex?\sigma%20(%20u%20,%20p%20)" /> indicate the tensor of the stresses, which for a Newtonian fluid is given by: <img src="https://latex.codecogs.com/svg.latex?\sigma(%20u%20,%20p%20)%20=%202%20\mu%20\epsilon%20(%20u%20)%20-%20p%20I" />


and where<img src="https://latex.codecogs.com/svg.latex?\epsilon%20(%20u%20)" />  is the tensor of the following strain rate:
<img src="https://latex.codecogs.com/svg.latex?\epsilon%20(%20u%20)%20=1/2(%20\nabla%20u%20+%20(%20\nabla%20u)^T)" />


# Results :
The following photos were obtained for a value of <img src="https://latex.codecogs.com/svg.latex?\nu=0.001"/>.

These are the results I got by taking a cylinder in the middle of the water flow channel. We could have taken another geometric shape to observe its impact on the evolution of the water flow.

We notice that there is the appearance of oscillations and that the fluid becomes turbulent at the outlet of the channel.
Besides, behind the cylinder one can notice that there are vortices (vortex which occurs in the fluid). These should be avoided because they considerably slow down the flow rate in the tube.

![vitesse+pression100](https://user-images.githubusercontent.com/72650161/113295401-72c52700-92f8-11eb-8580-89387b4eb642.png)
![vitesse+pression500](https://user-images.githubusercontent.com/72650161/113295419-78227180-92f8-11eb-818b-44c664d4e07d.png)
![vitesse+pression700](https://user-images.githubusercontent.com/72650161/113295433-7c4e8f00-92f8-11eb-97a8-2d7b719bf41f.png)
![vitesse+pression1200](https://user-images.githubusercontent.com/72650161/113295481-8b354180-92f8-11eb-820d-29be89d58e9e.png)
![vitesse+pression1500](https://user-images.githubusercontent.com/72650161/113295488-8ec8c880-92f8-11eb-9aee-88b5e974bb8f.png)
![vitesse+pression2500](https://user-images.githubusercontent.com/72650161/113295497-912b2280-92f8-11eb-8de1-421a21a52233.png)
![vitesse+pression2100](https://user-images.githubusercontent.com/72650161/113295492-8ff9f580-92f8-11eb-9cbe-449fc3c05756.png)
![vitesse+pression4980](https://user-images.githubusercontent.com/72650161/113295502-925c4f80-92f8-11eb-8009-856045c3c6f3.png)

# mu=0.005
Other simulation with a coefficient <img src="https://latex.codecogs.com/svg.latex?\nu=0.005"/> lead to the following results:
![vitesse+mu3200](https://user-images.githubusercontent.com/72650161/113295688-cf284680-92f8-11eb-8939-5027b138bcee.png)
We notice a kind of "trail" longer behind the cylinder.


# mu=0.0005
This simulation is performed for <img src="https://latex.codecogs.com/svg.latex?\nu=0.0005"/>.
We notice that it has less turbulence and that the flow is more laminar after the passage of the cylinder. It is deduced from this that this coefficient has an influence on the flow.
![vitesse+mu4980](https://user-images.githubusercontent.com/72650161/113295876-08f94d00-92f9-11eb-8987-90eade2f5574.png)


## Bibliography and references
The reference I used as a subject is:
- [DFG flow around cylinder](http://www.featflow.de/en/benchmarks/cfdbenchmarking/flow/dfg_benchmark2_re100.html)

The Fenics site for documentation of functions, examples and tutorials:
- [fenics Project](https://fenicsproject.org)


# Annex
Different results:
During the simulation, I obtained results as below when I used linear functions per piece as the definition space of V. But also when I used too large time steps the values also diverged.


![image_6](https://user-images.githubusercontent.com/72650161/113296007-35ad6480-92f9-11eb-93ee-507d5eb5296b.png)
