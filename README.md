## validation of tensile model (dog bone) with abaqus CAE program ##
Tensile Simulation Validation in Abaqus

👥 Authors
Eden Asis Nudel and Shira Hadad  
Computational Methods course
Tel Aviv University

📝 Project Overview
This project aims to validate a tensile simulation model created in Abaqus by comparing it to analytical, approximation using the finite element method (FEM) and experimental results. The focus is on evaluating the model's accuracy through different meshing resolutions and methods of solution.

🎯 Objective
To simulate the tensile behavior of a linear elastic material in Abaqus and validate the results against:
	Experimental tensile test data
	 Analytical calculations
	 Finite Element Method (FEM) formulation

🧪 Experimental Setup
A tensile test was conducted on a rectangular (the middle part of a 'dog bone' model) sample with the following dimensions:
	Length: 160 mm
	Width: 50 mm
	Thickness: 6 mm
	Reduced width in the center: 12.5 mm

Material properties:
	Young's Modulus (E): 7600 MPa
	Poisson's Ratio (ν): 0.29
	Applied Force (F): 25,000 N
Machine:
Zwick/Roell Z050, displacement controlled until fracture.
Result:
Yield stress = 397.836 MPa

🖥️ Simulation in Abaqus
Two simulations were performed using:
	Coarse mesh: Element size = 5 mm, 136 elements
	Fine mesh: Element size = 3.5 mm, 460 elements

Outputs:
	Displacement distribution along the X-axis
	Stress distribution under tensile load
	Force-displacement curves

Results:
	Coarse mesh: 
	Elongation = 2.193 mm
	Yield stress = 333.33 MPa
	Fine mesh:
	Elongation = 2.189 mm
	Yield stress = 397. 836 𝑀𝑃𝑎

📐 Analytical Solution
The elongation was calculated using the formula for an axially loaded bar:
ΔL =FL/EA
Where A is the cross-sectional area.
Result: 
Elongation = 2.193 mm

🧮 FEM Analytical Formulation
	1D bar discretized into 4 linear elements.
	Element stiffness: 
k^e=(E^e A^e)/h^e  (■(1&-1@-1&1))
	Assemble global, apply BCs and loads → solve.
Result:  
Elongation = 2.200 mm

📊 Results Comparison
Elongation comparison:
Method	Elongation [mm]
Experiment	2.188
Abaqus (fine mesh)	2.189
Abaqus (coarse mesh)	2.195
Analytical	2.193
FEM	2.200

Stress comparison:
Method	Young's Modulus [MPA]	Yield Stress [MPa]
Abaqus 	7600	333.33
Experimental	7755.25	397.84


✅ Conclusions
	High agreement (< 1 % error) among Abaqus (fine mesh), analytical, and FEM results for elastic elongation.
	Coarse mesh yields slightly higher error: fine mesh recommended for accuracy.
	Simulation underpredicts yield stress (~16 % lower) due to idealized linear elastic model and Poisson’s effect.
	Validates Abaqus as a reliable tool for linear elastic tensile analysis when mesh and material properties are well defined.
