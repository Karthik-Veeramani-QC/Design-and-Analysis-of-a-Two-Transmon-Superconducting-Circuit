# Design and Quantum Analysis of a Bus-Coupled Two-Transmon Superconducting Circuit

This repository contains the simulation data, analysis notebooks, and technical documentation for the design of a bus-coupled two-transmon superconducting circuit. The project demonstrates a complete workflow from physical layout in **Qiskit Metal** to full-wave electromagnetic simulation in **Ansys HFSS/Q3D**, and finally to quantum parameter extraction using the **Energy Participation Ratio (EPR)** method and **Lumped Oscillator Model (LOM)**.

Developed within the Department of Physics at IIT (BHU) Varanasi under the supervision of Dr. Rajeev Singh.

## 📁 Repository Contents

*   **`2_transmons_coupling_analysis_epr.ipynb`**: Jupyter notebook executing the Energy Participation Ratio (EPR) analysis via `pyEPR`. This script imports the HFSS eigenmode solutions to extract the multimode quantum Hamiltonian, including qubit anharmonicities and Kerr interactions.
*   **`2_transmons_coupling_analysis_lom.ipynb`**: Jupyter notebook performing a parametric study using the Lumped Oscillator Model (LOM). It utilizes the Q3D capacitance matrix to evaluate how coupling geometry impacts the dispersive shift and Purcell decay.
*   **`Data_used_for_graphs.xlsx`**: Raw datasets containing the parameter sweep results (coupling pad width and gap distance vs. coupling strength, dispersive shift, and $T_1$ times).
*   **`2 qubit report final.pdf`**: The comprehensive technical report detailing the theoretical background, methodology, and final results.

## 🔬 Architecture & Methodology

The circuit architecture consists of two capacitively shunted, fixed-frequency transmon qubits coupled via a common coplanar waveguide (CPW) bus resonator, with independent dispersive readout resonators and charge-bias lines. 

The analysis pipeline involves:
1.  **Layout Generation:** Procedural generation of the circuit geometry using Qiskit Metal.
2.  **Electromagnetic Simulation:** Extracting the first three eigenmodes using the Ansys HFSS Eigenmode solver and capacitance matrices via Q3D Extractor. 
3.  **Quantum Parameter Extraction:** 
    *   Using pyEPR to verify that the qubit modes are well-confined (negligible cross-participation) and to extract the static ZZ coupling.
    *   Using LOM to optimize the qubit-readout subsystem geometry.

## 📊 Key Results

*   **Qubit Regimes:** The extracted parameters confirm the circuit operates well within the transmon regime, with qubit frequencies near 5 GHz, anharmonicities of ~330 MHz, and an $E_J/E_C$ ratio of approximately 35.
*   **Bus Isolation:** The central bus resonator exhibits an anharmonicity of only 18.8 kHz, confirming it behaves as a linear interaction channel. The static ZZ coupling of -0.163 MHz indicates the qubits remain highly isolated during idle operation.
*   **Geometry Optimization:** Parameter sweeps identified an optimal coupling pad width of 60-75 μm and a coupling gap of 15-20 μm, providing an ideal balance between strong readout efficiency (dispersive shift) and coherence preservation (Purcell-limited relaxation).
