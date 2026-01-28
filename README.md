# NonLocalCorrelationTutorial

A light, hands-on set of notes and notebooks for my tutorial at **TIFR** on non-local correlations and quantum many-body numerics.

- School page: https://sites.google.com/view/nonlocalcorrelationsquantumsys/homepage
- Main theme: **tensor-network algorithms** for **ground-state search**, with a special focus on **DMRG**

> Tensor networks: because the full Hilbert space is very large, but our patience is not.


## What’s in here

This repository currently contains two Jupyter notebooks (using **Julia** + **ITensors.jl**) that build intuition and practical workflow:

1. **1D transverse-field Ising (TFI) chain**
   - Define a quantum wavefunction and spin-chain Hamiltonians as **MPS** and **MPO**.
   - Use **DMRG** to find ground states.
   - Explore **phases** and the **phase transition** by scanning parameters.
   - Observe the scaling **at criticality** of bond dimensions for systems that has large correlation lengths.

2. **2D system via snake-DMRG**
   - Map a 2D lattice to a 1D **“snake” ordering**.
   - Watch the **bond dimension** <sub>grow</sub> and grow and <strong><em>GROW</em></strong> with system size.

## Getting started

Clone this repo to your local machine: 
```bash
git clone https://github.com/SUTD-MDQS/NonLocalCorrelationTutorial.git
```

### 1. Installing Jupyter
If you don't have **JupyterLab** (or Jupyter Notebook) installed, you can do so via `pip` or `conda`.
**Prerequisites**: `pip` or `conda` commands installed in your terminal.
- Using `conda`:
   ```bash
   conda install -c conda-forge jupyterlab
   ```
- Using `pip`:
   ```bash
   pip install jupyterlab
   ```
*(I recommend against running the notebooks via VS Code Jupyter extension. Occasionally the notebook formatting gets complicated.)*
### 2. Installing Julia
   If not installed, you can install the official **Julia** language for your OS from [here](https://julialang.org/downloads/). Alternatively, you can also run these terminal commands based on your OS:
   - macOS: 
   ```bash
   brew install julia
   ```
   - Linux: 
   ```bash
   curl -fsSL https://install.julialang.org | sh
   ```
   - Windows (requires Microsoft Store): 
   ```powershell
   winget install --name Julia --id 9NJNWW8PVKMN -e -s msstore
   ```
### 3. Setting up Julia venv
This repo ships with a pinned Julia environment (`Project.toml`) to keep the packages we need consistent across laptops. 
**Prerequisites**: Julia v1.10 or higher installed and available in your terminal.
From the repo root, run:
```bash
julia --project=. -e 'using Pkg; Pkg.instantiate(); Pkg.precompile()'
```

### 4. Register the Julia kernel with Jupyter
To use the Julia environment in Jupyter notebooks, you need to register a new kernel. From the repo root, run:
```bash
julia --project=. -e 'using IJulia; IJulia.installkernel("Julia (NonLocalCorrelationTutorial)", env=Dict("JULIA_PROJECT"=>pwd()))'
```

### 5. Running the notebooks
   - Open JupyterLab/Notebook in the folder containing the notebooks.
   - Select the **Julia (NonLocalCorrelationTutorial)** kernel for the notebooks.

If everything ran without errors, you should now be ready to run the notebooks (whew!).

> **Laptop fan attempting lift-off?**  
> Try reducing the system sizes (your specs might not be sufficient).

## License

Unless stated otherwise in individual notebooks, feel free to use this material for learning and teaching, with attribution.
