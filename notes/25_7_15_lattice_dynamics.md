
# 📘 Summary of: *Lattice dynamics of anharmonic solids from first principles*  
**Authors**: O. Hellman, I. A. Abrikosov, and S. I. Simak  
**Published in**: *Phys. Rev. B 84, 180301(R) (2011)*  
**DOI**: [10.1103/PhysRevB.84.180301](https://doi.org/10.1103/PhysRevB.84.180301)

---

## 🔧 Background and Motivation

Understanding **phase equilibria** and **structural transformations** in solids under pressure and temperature is essential for materials science and geophysics. While **Density Functional Theory (DFT)** allows for accurate calculation of materials' properties, its ground-state nature limits its application to finite-temperature systems.

The **quasiharmonic approximation (QHA)** extends DFT by assuming a temperature-independent potential energy surface and computes temperature-dependent properties using volume-dependent phonon spectra. However, QHA fails in systems with:

- **Strong anharmonicity**
- **Dynamically unstable phases** at 0 K (e.g., imaginary phonon frequencies)

### 🔴 Problem:
When the harmonic or QHA approaches are used for such systems, they yield unphysical results — for example, imaginary phonon frequencies and undefined free energies. 

---

## ✅ Objective

To develop an **accurate and general method** to compute lattice dynamics and thermodynamic properties of solids at finite temperatures, even for **dynamically unstable and strongly anharmonic systems**, directly from **first-principles molecular dynamics (AIMD)**.

---

## ⚙️ Theoretical Framework

The method constructs a **temperature-dependent harmonic approximation** by fitting forces and displacements from AIMD trajectories to obtain an effective potential energy surface.

### 🔸 Standard Harmonic Approximation

Taylor expansion of the potential energy \( U \) at 0 K:

\[
U = U_0 + \frac{1}{2} \sum_{i,j,\mu,\nu} u_{\mu}(\mathbf{R}_i) \frac{\partial^2 U}{\partial u_{\mu}(\mathbf{R}_i)\partial u_{\nu}(\mathbf{R}_j)} u_{\nu}(\mathbf{R}_j) + \cdots
\]

Where:

- \( u_{\mu}(\mathbf{R}_i) \): displacement of atom \( i \) in direction \( \mu \)
- \( D_{ij}^{\mu\nu} = \frac{\partial^2 U}{\partial u_{\mu}(\mathbf{R}_i)\partial u_{\nu}(\mathbf{R}_j)} \): force constant matrix

---

## 🔍 Methodology

### 1. **Finite-T Effective Force Constants**

From AIMD data, extract the effective force constant matrix \( \tilde{D} \) via least squares fitting of the second-order force expression:

\[
\mathbf{F}_i^{(t)} \approx -\sum_j \tilde{D}_{ij} \cdot \mathbf{u}_j^{(t)}
\]

Objective function minimized:

\[
\Delta F = \sum_{t,i} \frac{1}{N_t} \left| \mathbf{F}_i^{(t)} - \tilde{\mathbf{F}}_i^{(t)} \right|
\]

If the number of time steps \( N_t > 3N_a \), the system is overdetermined and solved via least squares.

### 2. **Symmetry Enforcement**

To reduce numerical noise and enhance stability, the computed force constants are symmetrized using lattice point group symmetry and mapping to coordination shells.

---

## 📈 Results

### 🔬 Accuracy of Fit

- Convergence tested by increasing simulation time.
- After ~40 ps (20,000 steps), free energy converges within 0.5 meV/atom — below DFT noise level.
- The Frobenius norm of nearest-neighbor force constants stabilizes.

### 📊 Figure 1:

- Shows convergence of free energy and force constants with simulation time.
- Demonstrates robustness of the method.

---

## 🔊 Phonon Spectra: bcc-Li and bcc-Zr

- bcc-Li: QHA at 0 K yields **imaginary frequencies**.
- Using the present method at 300 K removes all imaginary frequencies.
- Excellent match with **experimental phonon dispersion**.

- bcc-Zr: Soft phonon mode at the **ω-point** in the H–P direction captured accurately.
- This mode is crucial for the **bcc → ω phase transition** in Zr.

---

## 🧪 Phase Diagram: hcp–bcc Transition in Zr

- Free energy surfaces calculated for:
  - bcc-Zr using this method on a grid of 6 volumes × 5 temperatures (100–1700 K)
  - hcp-Zr using QHA (since hcp is dynamically stable)

- Gibbs free energy computed as:

\[
G(T, P) = F(T, V) + PV
\]

- At each T, the phase with lowest G is selected.
- Resulting **hcp–bcc phase boundary** agrees extremely well with experiment.

---

## 🧠 Key Insights

- The method **does not rely on expansion at 0 K**, unlike QHA.
- Though formally harmonic (2nd order), it incorporates **temperature-dependent anharmonic effects** via renormalized phonon frequencies.
- It can be **extended to include higher-order terms** if needed.

---

## 📌 Conclusion

This work presents a **general, accurate, and extendable framework** to extract the **best harmonic approximation** to the true anharmonic potential energy surface at any finite temperature:

✅ Captures stabilization of dynamically unstable phases  
✅ Computes accurate phonon spectra and thermodynamic quantities  
✅ Predicts phase transitions (e.g., hcp–bcc in Zr) in strong agreement with experiments

This approach bridges a crucial gap in lattice dynamics for **anharmonic solids** where traditional approximations fail.

---

## 📚 References

Key references include:
- [2] Wallace, Thermodynamics of Crystals
- [3] Baroni et al., DFPT
- [12] Souvatzis et al., self-consistent ab initio lattice dynamics
- [17] Alfè et al., small displacement method
- [22–25] VASP and PAW implementation

