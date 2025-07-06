# Structural phase transitions in SrTiO₃ from deep potential molecular dynamics

## Summary

This study develops a **Deep Potential (DP)** model trained on **DFT (PBEsol)** data to investigate the structural and ferroelectric phase transitions in **SrTiO₃ (STO)** at finite temperatures and under in-plane biaxial strain. The work focuses on achieving DFT-level accuracy while enabling efficient molecular dynamics simulations over larger time and length scales.

---

## Key Contributions

- **Model Development**:  
  A DP model is trained using a large dataset of atomic configurations and energies from DFT. The model achieves high accuracy in reproducing energies, forces, phonon dispersions, and structural properties.

- **Validation**:  
  The DP model reproduces:
  - Lattice constants within 0.004 Å of DFT
  - Energy differences between cubic and tetragonal phases within 0.1 meV/atom
  - Phonon dispersions, including unstable AFD (R⁻₅) and polar (Γ⁻₄) modes
  - Elastic constants and equation of state consistent with DFT

- **Phase Transitions**:
  - Simulations capture the temperature-driven **tetragonal-to-cubic** phase transition
  - The critical temperature is predicted around **190 K** (vs. 105 K experimentally)
  - Discrepancy attributed to missing nuclear quantum effects in classical MD

- **Strain Effects**:
  - A detailed **strain-temperature phase diagram** is constructed
  - **Compressive strain (>0.2%)** induces **out-of-plane polarization (Pz)** and AFD along [001]
  - **Tensile strain** favors **in-plane polarization (Px, Py)** and AFD along [100]/[010]
  - FE transition temperature increases linearly with strain
  - **Room-temperature ferroelectricity** predicted at 1.4% tensile or 2.3% compressive strain

- **Transition Mechanism**:
  - The FE transition under strain exhibits **both displacive and order–disorder** characteristics
  - Polarization distributions confirm long-range order at low T and dipole flipping near Tc

---

## Conclusions

The study provides atomistic insight into structural and ferroelectric transitions in SrTiO₃, and demonstrates that **machine learning-based potentials** like DP can bridge the gap between DFT accuracy and MD-scale simulation efficiency. This approach is promising for modeling complex perovskite oxides beyond STO.

---

## Citation

*Title*: Structural phase transitions in SrTiO₃ from deep potential molecular dynamics  
*Methods*: Deep Potential Molecular Dynamics (DPMD), DFT (PBEsol)  
*Keywords*: SrTiO₃, structural phase transition, ferroelectricity, AFD, DPMD, machine learning interatomic potential
