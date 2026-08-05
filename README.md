# Design and Analysis of a Bus-Coupled Two-Transmon Superconducting Circuit

This repository contains the design files, Python notebooks, and report for the analysis of a bus-coupled two-transmon superconducting circuit. The project investigates the effect of readout coupling geometry on qubit frequencies, dispersive shift, coupling strength, and Purcell-limited relaxation using full-wave electromagnetic simulations and quantum parameter extraction.

<p align="center">
  <img src="images/circuit_two_transmons.png" width="750">
</p>

## Repository Structure

- **2_transmons_coupling_analysis_epr.ipynb** – Quantum Hamiltonian extraction (frequencies, anharmonicities and Kerr interactions) using pyEPR.
- **2_transmons_coupling_analysis_lom.ipynb** – Lumped Oscillator Model (LOM) analysis of dispersive shift, coupling strength and Purcell decay using Q3D capacitance matrices.
- **Data_used_for_graphs.xlsx** – Parameter sweep data.
- **2_qubit_report_final.pdf** – Complete project report.

## Workflow

```
Qiskit Metal
      ↓
HFSS Eigenmode + Q3D
      ↓
pyEPR / LOM
      ↓
Quantum Hamiltonian
      ↓
Geometry Optimization
```

## Methods

- Circuit Layout: Qiskit Metal
- Electromagnetic Simulation: Ansys HFSS (Eigenmode) and Q3D Extractor
- Quantum Analysis: pyEPR and Lumped Oscillator Model (LOM)

## Key Results

| Parameter | Value |
|-----------|------:|
| Qubit Frequencies | 4.646 GHz, 4.858 GHz |
| Anharmonicities | 327.23 MHz, 326.27 MHz |
| \(E_J/E_C\) | ~35 |
| Bus Anharmonicity | 18.8 kHz |
| Static ZZ Coupling | -0.163 MHz |

### Readout Geometry

Increasing the coupling pad width from **30 μm to 100 μm** increased the coupling strength from **55 MHz to 91 MHz** and the dispersive shift from **0.27 MHz to 0.72 MHz**, but reduced the Purcell-limited relaxation time from **~900 μs to ~330 μs**.

The optimum design was obtained for a coupling pad width of **60–75 μm** with a coupling gap of **15–20 μm**, providing a balance between readout strength and qubit coherence.

## Report

A detailed description of the methodology, simulations, and results is available in **2_qubit_report_final.pdf**.
