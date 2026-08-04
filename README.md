# Design and Analysis of a Bus-Coupled Two-Transmon Superconducting Circuit

This repository contains the Python notebooks, parameter sweep data, and final report for the design and quantum parameter extraction of a two-transmon circuit. 

## Files
*   **`2_transmons_coupling_analysis_epr.ipynb`**: Extracts the quantum Hamiltonian (frequencies, anharmonicities, and Kerr interactions) from HFSS eigenmode data using pyEPR.
*   **`2_transmons_coupling_analysis_lom.ipynb`**: Evaluates the effect of readout coupling geometry on dispersive shift and Purcell decay using the Lumped Oscillator Model (LOM) and Q3D capacitance matrices.
*   **`Data_used_for_graphs.xlsx`**: Raw data from the geometric parameter sweeps.
*   **`2 qubit report final.pdf`**: Final project report detailing the full methodology and results.

## Methods Used
*   **Circuit Layout:** Qiskit Metal.
*   **Electromagnetic Simulation:** Ansys HFSS (Eigenmode solver) and Q3D Extractor.
*   **Quantum Analysis:** Energy Participation Ratio (EPR) via pyEPR and Lumped Oscillator Model (LOM).

## Key Results
*   **Qubit Parameters & Regime:** The extracted qubit frequencies are 4.646 GHz and 4.858 GHz, with anharmonicities of 327.23 MHz and 326.27 MHz[cite: 4]. The calculated $E_J/E_C$ ratio of approximately 35 confirms the circuit operates strictly within the transmon regime.
*   **Bus Isolation:** The central bus resonator has a negligible anharmonicity of 18.8 kHz, verifying it acts as a linear microwave resonator[cite: 4]. The static ZZ coupling is -0.163 MHz, indicating the qubits remain well-isolated during idle operation.
*   **Readout Geometry & Purcell Decay:** LOM sweeps revealed a direct trade-off between readout efficiency and coherence[cite: 4]. Increasing the coupling pad width (30 to 100 μm) increased the dispersive shift from 0.27 MHz to 0.72 MHz and coupling strength from 55 MHz to 91 MHz, but drastically reduced the Purcell-limited relaxation time ($T_1$) from nearly 900 μs to 330 μs[cite: 4]. An optimal balance is achieved using a coupling pad width of 60-75 μm and a coupling gap of 15-20 μm.

## What I Learned
Through this project, I learned how to bridge the gap between abstract quantum circuits and physical microwave engineering. Designing the layout taught me the practical constraints of planar geometries, and I gained hands-on experience using Ansys HFSS and Q3D to simulate electromagnetic fields and extract capacitance matrices. Most importantly, running the EPR and LOM pipelines helped me understand the physical origins of quantum parameters. I learned how to systematically analyze engineering trade-offs, particularly how pushing for a stronger readout signal inherently sacrifices qubit coherence time through the Purcell effect.
