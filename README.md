# Design and Analysis of a Bus-Coupled Two-Transmon Superconducting Circuit

This repository contains the Python notebooks, parameter sweep data, and final report for the design and quantum parameter extraction of a two-transmon circuit[cite: 4]. 

## Files
*   **`2_transmons_coupling_analysis_epr.ipynb`**: Extracts the quantum Hamiltonian (frequencies, anharmonicities, and Kerr interactions) from HFSS eigenmode data using pyEPR.
*   **`2_transmons_coupling_analysis_lom.ipynb`**: Evaluates the effect of readout coupling geometry on dispersive shift and Purcell decay using the Lumped Oscillator Model (LOM) and Q3D capacitance matrices.
*   **`Data_used_for_graphs.xlsx`**: Raw data from the geometric parameter sweeps.
*   **`2 qubit report final.pdf`**: Final project report detailing the full methodology and results.

## Methods Used
*   **Circuit Layout:** Qiskit Metal[cite: 4]
*   **Electromagnetic Simulation:** Ansys HFSS (Eigenmode solver) and Q3D Extractor[cite: 4]
*   **Quantum Analysis:** Energy Participation Ratio (EPR) via pyEPR and Lumped Oscillator Model (LOM)[cite: 4]

## Key Results
*   **Qubit Parameters:** The extracted qubit frequencies are near 5 GHz with anharmonicities of approximately 330 MHz and an $E_J/E_C$ ratio of ~35, placing the circuit well within the transmon regime[cite: 4].
*   **Bus Isolation:** The central bus resonator has an anharmonicity of 18.8 kHz, confirming it operates as a linear microwave resonator[cite: 4]. The static ZZ coupling is -0.163 MHz, indicating the qubits remain largely isolated during idle operation[cite: 4].
*   **Geometry Optimization:** LOM sweeps indicated that a readout coupling pad width of 60-75 μm and a coupling gap of 15-20 μm provides a suitable balance between readout coupling strength (55-90 MHz) and Purcell-limited relaxation time[cite: 4].
