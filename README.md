# NonLocalCorrelationTutorial

A light, hands-on set of notes and notebooks for my tutorial at **TIFR** on non-local correlations and quantum many-body numerics.

- School page: https://sites.google.com/view/nonlocalcorrelationsquantumsys/homepage
- Main theme: **tensor-network algorithms** for **ground-state search**, with a special focus on **DMRG**

> Tensor networks: because the full Hilbert space is very large, but our patience is not.

---

## What’s in here

This repository currently contains two Jupyter notebooks (using **Julia** + **ITensors.jl**) that build intuition and practical workflow:

1. **1D transverse-field Ising (TFI) chain**
   - Define a quantum wavefunction and spin-chain Hamiltonians as MPS and MPO
   - Use DMRG to find ground states
   - Explore phases and the phase transition by scanning parameters
   - Observe the scaling of bond dimensions for systems that has large correlation lengths (at criticality)

2. **2D system via snake-DMRG**
   - Map a 2D lattice to a 1D “snake” ordering
   - Watch the **bond dimension** grow… and grow… and grow with system size


> **Laptop fan attempting lift-off?**  
> Try reducing the system sizes (your specs might not be sufficient).

---

## Getting started (quick)

### 1. Installing Jupyter
Install **JupyterLab** (or Jupyter Notebook) and run the notebooks from your browser.  
   *(I recommend avoiding the VS Code Jupyter extension here—occasionally the notebook formatting gets a little… quantum.)*
### 2. Installing Julia
   - macOS: `brew install julia`
   - Linux: use your distro package manager, or download from https://julialang.org/downloads/
   - Windows: install from https://julialang.org/downloads/ (or `winget install Julia -s winget`)
### 3. Installing **ITensors.jl**
   - Start Julia, then:
     ```julia
     using Pkg
     Pkg.add("ITensors")
     ```
   Better to create a reproducible setup for a class, create a local environment (`Project.toml`/`Manifest.toml`) and `Pkg.instantiate()`.
### 4. Running the notebooks
   - Open JupyterLab/Notebook in the folder containing the notebooks.
   - Select the Julia kernel for the notebooks.

---

## License

Unless stated otherwise in individual notebooks, feel free to use this material for learning and teaching, with attribution.
