# MPC-discretization-analysis-through-different-Runge-Kutta-methods
Discretization through different Runge-Kutta methods for Model Predictive Control (MPC) implementation. Comparison of three main models: Euler (standard use), Heun and RK4. 

To compare the methods a linearized model of a pendulum has been used. 

$\frac{d^2\theta}{dt^2}=-\frac{g}{L}sin(\theta)+u$ 

"u" is the input. Linearized around $\theta=0$. 

# Installation/Requirements
Through colab, the code is already set for it to be ran directly 

# Usage

To change physical conditions to observe different behaviors from controller, change the length of the pendulum ($L$). 
It is also interesting to change time step ($Ts$)to see precision and feasibility change from the three methods. 

## Analyzing data

After the MPC calculations, the program executes a display with 6 graphs called "State (theta) and imput (u) subject to time" comparing all RK methods. In the default setup (L=1m, Ts=0.1s), Euler method is infeasible, while Heun an RK4 don't appear to have significant changes.  In the subtitle you can read the elapsed time, which is a performance indicator for each method. 

As a takeaway from this specific example, the higher the degree of the RK method, the lesser computing time and more fidelity to be able to generate a feasible optimization problem. To check how RK4 is better than Heun, type $Ts=0.5$. 

The second display called "Trajectory according to different models" creates a 3-graph feature that explains the evolution of the position prediction according to the executed inputs for each model. The linearized model around $/theta=0$ is the least accurate comparing it with the ODE solver solution (blue). As for the value marked on top of each graph called "Cost=_" indicates the terminal cost of each minimization problem for MPC. 

This example shows better performance for prediction of state and cost function for the higher degree methods. 

# Mathematical proof

See text file


