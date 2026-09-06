[README (2).md](https://github.com/user-attachments/files/31882565/README.2.md)[Upl# CFD Simulation of Flow Around a GT Spoiler using SimScale

This project demonstrates a complete Computational Fluid Dynamics (CFD) workflow for incompressible flow around a GT car spoiler using SimScale, a cloud-based engineering simulation platform. The project was completed as part of the Coursera hands-on project platform (Rhyme) which provides pre-configured cloud desktops with all necessary tools.

### Project Preview

**Post-processing - Particle Traces Colored by Velocity Magnitude**
Flow visualization showing streamlines deflecting over the spoiler surface, demonstrating downforce generation. Streamlines are colored by velocity magnitude (green = low/medium velocity, yellow/blue = accelerated flow regions).

**Convergence & Solver Monitoring**
Monitored residuals for velocity components (Ux, Uy, Uz), pressure (p), turbulent kinetic energy (k), and specific dissipation rate (omega) over 1000 iterations to ensure convergence and stability.

---

### Project Objectives

- Understand fundamentals of Computational Fluid Dynamics (CFD)
- Learn the classical 3-step CFD workflow: Pre-processing, Processing, Post-processing
- Set up an external aerodynamics case for a GT spoiler
- Apply and understand boundary conditions for incompressible flow
- Analyze aerodynamic behavior, flow separation, and downforce generation
- Use SimScale's cloud-based post-processor for visualization

### Tools & Platform

- **Simulation Platform:** [SimScale](https://www.simscale.com/) - Cloud-based, browser-accessible
- **Physics Model:** Incompressible Fluid Flow (Steady-State / RANS)
- **Learning Platform:** Coursera + Rhyme (Hands-on Cloud Desktops)
- **Turbulence Model:** k-omega SST (inferred from residuals k & omega)
- **Solver:** SIMPLE-based incompressible solver

### Geometry

- **Model:** GT Spoiler / Rear Wing with endplates and central mount
- **Domain:** External flow region enclosing the spoiler (Flow region)
- **Provided as:** Pre-imported CAD in SimScale project `coursera - Project around a GT Spoiler`

### Workflow & Simulation Setup

#### 1. Pre-processing

**a) Mesh Generation:**
- Generated finite volume mesh around the spoiler
- Flow region defined as the computational domain
- Local refinements around spoiler walls and wake region to capture boundary layer

**b) Physics Setup:**
- Material: Air (Incompressible, Newtonian)
  - Density: 1.225 kg/m3
  - Kinematic viscosity: 1.48e-5 m2/s
- Model: Steady-state, Turbulent

**c) Initial Conditions:**
- Initial velocity field set to freestream value
- Initial pressure = 0 Pa (gauge)

**d) Boundary Conditions (As seen in simulation tree):**
| Boundary | Type | Purpose |
|----------|------|---------|
| **Spoiler** | Wall (No-slip) | Solid surface of the spoiler |
| **Ext. Walls** | Wall / Slip | Far-field enclosure |
| **Velocity Inlet 3** | Velocity Inlet | Defines freestream velocity approaching the spoiler |
| **Pressure Outlet 4** | Pressure Outlet | Defines downstream pressure, allows flow exit |
| **Moving Wall** | Moving Wall | Simulates moving ground / road condition |
| **Symmetry 6** | Symmetry | Reduces computational cost by simulating half-model |

**e) Numerics & Simulation Control:**
- Convergence criteria, discretization schemes, and solver settings configured for stability
- 1000 iterations defined for solution convergence

#### 2. Processing (Solving)

- **Run 1** executed on SimScale cloud cores
- Monitored convergence via:
  - **Domain, Inlets, Outlets, Walls:** Convergence of Ux, Uy, Uz, and p
  - **Residuals Plot:** Final residuals for Ux, Uy, Uz ~ 1e-3, p ~ 1.5e-2, k ~ 5e-4, omega ~ 1e-5 indicating good convergence
- Solver Log checked for errors and continuity

#### 3. Post-processing

Performed in SimScale's online post-processor:

- **Particle Traces / Streamlines:** 
  - 5x5 seeds with spacing 2.7e-2
  - Colored by Velocity Magnitude, represented as Cylinders (Size 3e-3)
  - Visualized flow deflection, acceleration over the top surface, and wake behind the spoiler

- **Cutting Plane:** Used to inspect velocity and pressure fields around airfoil section

- **Iso Surface / Iso Volume:** To visualize pressure distribution and vortex structures

- **Forces:** Downforce (negative lift) and drag can be extracted from Result Control

### Key Results & Insights

1. **Flow Pattern:** Streamlines remain attached over most of the spoiler, with clear downwash behind the trailing edge - essential for generating downforce.
2. **Velocity Distribution:** Acceleration observed over the upper surface of the spoiler, with lower velocity region underneath confirming pressure differential.
3. **Convergence Behavior:** The residual plots showed initial fluctuations (0-150 iterations) followed by stable convergence after ~600 iterations. Pressure and velocity components stabilized, indicating a physically realistic steady-state solution.
4. **Aerodynamic Function:** The GT spoiler works as an inverted wing - high pressure above, low pressure below, resulting in net downward force that improves traction at high speeds.

### How to Reproduce This Project

1. Create a free SimScale account (Community Plan available)
2. Import the provided GT Spoiler geometry
3. Create External Aerodynamics > Incompressible simulation
4. Set up mesh: Automatic hex-dominant with local refinement on spoiler
5. Assign Air material and set boundary conditions as listed above
6. Run 1000 iterations
7. Use Post-processor > Particle Trace to visualize as shown

No local installation needed - everything runs in the browser via Rhyme/Coursera or SimScale.

### Key Learnings

- Difference between pre-processing, processing, post-processing in CFD
- How to select appropriate boundary conditions for external aerodynamics
- Importance of mesh refinement and convergence monitoring
- How to interpret residuals and convergence plots
- Practical use of SimScale for rapid, cloud-based CFD without HPC setup
- Visual interpretation of downforce generation mechanism

### Future Improvements

- Perform mesh independence study
- Run parametric study for different Angle of Attack (AoA)
- Calculate and plot Cd (Drag Coefficient) and Cl (Downforce Coefficient)
- Compare k-epsilon vs k-omega SST turbulence models
- Add transient analysis to capture vortex shedding

### Author

**Project Completed By:** Govindaswamy (as seen in SimScale workspace)
**Course:** CFD Simulation Around a GT Spoiler - Coursera Project Network / Rhyme
**Platform:** SimScale

### Acknowledgments

- Coursera & Rhyme for providing hands-on cloud environment
- SimScale team for the accessible CFD platform and documentation
- Course instructor for GT Spoiler geometry and guided setup

---

**License:** For educational purposes.
oading README (2).md…]()
