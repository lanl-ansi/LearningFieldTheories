# LearningFieldTheories
This repository contains Julia implementations of classical and gauge lattice field theories with explicit sampling, parameter learning, and renormalization-group (RG) flow analysis. The goal is to unify statistical inference and field-theoretic RG methods, demonstrating how coupling constants and effective Hamiltonians can be learned directly from simulated or experimental data.

| Model                                     | Dimension | Description / Key Features                                                                                                                                      |
| ----------------------------------------- | --------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1D Ising Model**                        | 1D        | Analytical baseline; Metropolis sampling; learning using Pseudolikelihood (PL) and RISE estimators; error-scaling and RG analysis.            |
| **2D Schwinger Model**                    | 2D        | Gauge + fermion formulation; parameter and RG inference (β, m) via score matching; demonstrates gauge–matter coupling learning.                                        |
| **Dual Schwinger Model**                  | 2D        | Scalar field representation; RG flow reconstruction and error analysis.                                                     |
| **2D Sine-Gordon Model**                  | 2D        | Sampling using Metropolis, learning β-functions via score matching; comparison with analytical RG predictions and phase boundary.                         |
| **2D Wegner’s Ising Gauge Theory (WIGT)** | 2D        | Link-variable lattice gauge theory; implemented with Metropolis and Cluster algorithms; Wilson-loop and string-tension estimation; various RG blocking schemes. |
| **2D Z₂ Higgs Model**                     | 2D        | Coupled matter–gauge system; spontaneous symmetry breaking and confinement; joint sampling of link and matter fields.                                           |

## Key Results

- Demonstrates that models with **discrete, continuous or mixed data** can be learned directly from Monte Carlo samples and from moments only.  
- Recovers known **RG fixed points** and **scaling laws** for the learned couplings.  
- Extracts **string tension** from Wilson-loop expectation values, confirming the **area-law confinement** behavior.  
- Establishes **error-scaling** with sample size, following \( |\hat{K} - K| \propto N^{-1/2} \).  
- Connects **gauge dualities** (Schwinger ↔ Dual Schwinger) with **learned coarse-grained couplings** along the RG flow.
- Learns **new non-perturbative behavior** about relevant and irrelevant operators.  

## Design and Methodology

### Sampling
Metropolis, Heatbath, and Cluster (Swendsen–Wang / Wolff-type) algorithms are implemented for efficient exploration of the configuration space.  
For gauge models, sampling is performed over **link variables**, while for scalar and spin models, **site variables** are updated using local or cluster moves.

### Learning
Coupling constants and effective Hamiltonians are learned directly from sampled data using **Pseudolikelihood (PL)**, and **Score Matching** estimators.  
These estimators minimize analytical loss functions derived from the log-likelihood or score function, allowing **parameter reconstruction** without explicit partition function evaluation.

### Renormalization Group (RG) Learning
Several **coarse-graining schemes** are implemented — including block-spin transformations, plaquette blocking, and checkerboard mappings — to derive scale-dependent effective couplings.  
Learned couplings across RG steps yield RG flows that reproduce analytical results, or show new higher order/non-perturbative effects.

### Observables and Diagnostics
Physical quantities such as **plaquette energy**, **autocorrelation functions**, **Wilson loops**, and **string tension** are computed to monitor equilibrium and confinement behavior.  
Diagnostic tools include **error-scaling with sample size**, **autocorrelation time estimation**, and **RG fixed-point detection**.

Together, these components demonstrate how **data-driven learning** recovers **renormalization behavior**, **universality**, and **confinement properties** from raw lattice configurations.

## License
This code is provided under a BSD license as part of the Optimization, Inference and Learning for Advanced Networks project, C18014.

## Citation
If you use this repository in your work, please cite:
```bibtex
@misc{LSFT2025,
      title        = {Learning of Statistical Field Theories},
      author       = {Shreya Shukla and Abhijith Jayakumar and Andrey Y. Lokhov},
      year         = {2025},
      eprint       = {2511.09859},
      archivePrefix= {arXiv},
      primaryClass = {cond-mat.stat-mech},
      url          = {https://arxiv.org/abs/2511.09859}
}
