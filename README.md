# LearningFieldTheories
This repository contains Julia implementations of classical and gauge lattice field theories with explicit sampling, parameter learning, and renormalization-group (RG) flow analysis. The goal is to unify statistical inference and field-theoretic RG methods, demonstrating how coupling constants and effective Hamiltonians can be learned directly from simulated data.

| Model                                     | Dimension | Description / Key Features                                                                                                                                      |
| ----------------------------------------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1D Ising Model**                        | 1D        | Analytical baseline; Metropolis sampling; learning using Pseudolikelihood (PL) and RISE estimators; error-scaling and RG analysis.            |
| **2D Schwinger Model**                    | 2D        | Gauge + fermion formulation; parameter and RG inference (β, m) via score matching; demonstrates gauge–matter coupling learning.                                        |
| **Dual Schwinger Model**                  | 2D        | Scalar field representation; RG flow reconstruction and error analysis.                                                     |
| **2D Sine-Gordon Model**                  | 2D        | Sampling using Metropolis, learning β-functions via score matching; comparison with analytical RG predictions and phase boundary.                         |
| **2D Wegner’s Ising Gauge Theory (WIGT)** | 2D        | Link-variable lattice gauge theory; implemented with Metropolis and Cluster algorithms; Wilson-loop and string-tension estimation; various RG blocking schemes. |
| **2D Z₂ Higgs Model**                     | 2D        | Coupled matter–gauge system; spontaneous symmetry breaking and confinement; joint sampling of link and matter fields.                                           |

Key Results

Demonstrates that inverse Ising and inverse gauge models can be learned directly from Monte Carlo samples.

Recovers known RG fixed points and scaling laws for learned couplings.

Extracts string tension from Wilson-loop expectation values, showing area-law confinement.

Establishes error-scaling with sample sizes.

Connects gauge dualities (Schwinger ↔ Dual Schwinger) with learned coarse-grained couplings.
