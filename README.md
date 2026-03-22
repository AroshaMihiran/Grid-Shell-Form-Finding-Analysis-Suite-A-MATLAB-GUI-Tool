# GridShell-Analysis-Suite-MATLAB-GUI-Tools-for-Timber-Grid-Shell-Structural-Design
MATLAB GUI toolkit for timber grid shell design using the Potential Energy Method. Includes Form Finding Tool (FFT) and Coupled Analysis Tool (CAT) with Member Sizing. Features a three-panel interface with interactive controls, data tables, and real-time 3D visualisation. 

A comprehensive MATLAB-based graphical toolkit for the structural analysis and design of timber grid shell structures using the Potential Energy Method (PEM). This repository provides two standalone GUI applications that streamline the complete workflow from geometric definition through form finding and coupled structural analysis, addressing key limitations in existing PEM implementations.
GridShell Form Finding Tool (FFT) performs form finding by minimising total potential energy to determine equilibrium shell geometries. Unlike conventional implementations that assume uniform material properties across all members, this tool enables individual assignment of Young's modulus (E) and cross-sectional area (A) to each member independently. Users define a planar grid, select nodes with boundary constraints, assign heterogeneous material properties and member-specific cross-sectional areas, and apply distinct load patterns to individual panels. The tool produces a structurally efficient curved geometry from an initially flat configuration, supporting arbitrary grid shell topologies rather than being restricted to specific configurations.
GridShell Coupled Analysis Tool (CAT) extends the workflow to address the fundamental problem of uncoupled stiffness and geometry in statically indeterminate structures. When members are resized during design verification, their axial stiffness (EA/L) changes, redistributing internal forces and invalidating the original equilibrium geometry. The CAT implements an iterative coupled form-finding and member-sizing procedure that dynamically updates member stiffness properties during the process, alternating between geometry optimisation and code-compliant member sizing until convergence is achieved, delivering structurally valid designs where geometry and member capacities are mutually consistent.
Both tools share a unified three-panel interface comprising interactive controls, editable data tables, and real-time 3D visualisation.

Designed for researchers, engineers, and students working on lightweight timber structures, architectural geometry, and computational structural mechanics.

Here's the cleaned-up version:

Getting Started
Prerequisites

MATLAB (R2020a or later recommended)
Optimization Toolbox — the computational backend uses fminunc for potential energy minimisation

Directory Structure
All scripts and helper functions must reside in the same parent directory:
/GridShell_Analysis/
├── GridShellAnalysisTool.m                      % CAT GUI
├── GridShellAnalysisTool_FormFindingOnly.m      % FFT GUI
├── RunGridShellAnalysis.m                       % CAT backend
├── RunGridShellFormFinding.m                    % FFT backend
├── gridshell_panels.m
├── gridshell_panels_loads.m
└── /FFMS/                                       % Helper functions
    ├── GetL.m
    ├── GetNepsZdof.m
    └── GetPotential.m
Launching the Tools
Open MATLAB and set the current folder to GridShell_Analysis. Then run either command in the Command Window:
ToolCommandForm Finding Tool (FFT)GridShellAnalysisTool_FormFindingOnlyCoupled Analysis Tool (CAT)GridShellAnalysisTool
The GUI window will open with three panels: controls on the left, data tables in the centre, and 3D visualisation on the right. Follow the numbered sections in the controls panel from top to bottom to define your grid shell and run the analysis.

