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
*   **Qubit Parameters & Regime:** The extracted qubit frequencies are 4.646 GHz and 4.858 GHz, with anharmonicities of 327.23 MHz and 326.27 MHz. The calculated $E_J/E_C$ ratio of approximately 35 confirms the circuit operates strictly within the transmon regime.
*   **Bus Isolation:** The central bus resonator has a negligible anharmonicity of 18.8 kHz, verifying it acts as a linear microwave resonator. The static ZZ coupling is -0.163 MHz, indicating the qubits remain well-isolated during idle operation.
*   **Readout Geometry & Purcell Decay:** LOM sweeps revealed a direct trade-off between readout efficiency and coherence. Increasing the coupling pad width (30 to 100 μm) increased the dispersive shift from 0.27 MHz to 0.72 MHz and coupling strength from 55 MHz to 91 MHz, but drastically reduced the Purcell-limited relaxation time ($T_1$) from nearly 900 μs to 330 μs. An optimal balance is achieved using a coupling pad width of 60-75 μm and a coupling gap of 15-20 μm.

## What I Learned
This project taught me the practical workflow of taking a theoretical circuit and turning it into a physical layout. I learned how to extract raw electromagnetic modes and capacitance matrices from Ansys HFSS and Q3D, and how to actually translate those into a quantum Hamiltonian using pyEPR. It also gave me a much clearer understanding of the Purcell effect in practice. Seeing how just tweaking the physical geometry to get a better readout signal directly ruins the qubit's $T_1$ time, and figuring out how to optimize that trade-off.
