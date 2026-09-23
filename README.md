# Types of Bursting with a Two-Block Spiking Primitive

## About this repository

This repository contains all code involved in **Types of Bursting with a Two-Block Spiking Primitive**.

The paper studies a minimal excitable system: a static nonlinearity of gain `k` closed in positive feedback around a linear frequency selector `H(s)` that blocks the constant component of its input. Two selectors are treated, a first-order high-pass with a saturation, and a second-order resonant band-pass with a `tanh`. The nonlinearity decides whether the cell fires and where the threshold sits. The selector decides whether rest and firing can coexist, hence which burst class is available.

## Getting started

This work uses the [Julia programming language](https://julialang.org/). To set up the environment, download Julia, then open a Julia REPL, navigate to this repository, and run:

```jl
using Pkg
Pkg.add(["Plots", "LaTeXStrings", "DifferentialEquations", "DiffEqCallbacks",
         "ProgressMeter", "IJulia"])
```

This will install all required packages. `Printf` and `Statistics` ship with Julia.

## Repository structure

Everything sits at the top level. Each notebook is self-contained and can be run on its own, in any order.

| Notebook | Description | Figure |
|---|---|---|
| `simulate_neuron.ipynb` | The loop with the high-pass selector, three minimal examples: tonic firing, the firing band, a slow sweep across it | |
| `simulate_neuron_bursting.ipynb` | Parabolic bursting with the high-pass selector, exogenous drive and the cascade of two copies of the primitive | Fig. 3 |
| `simulate_neuron_typeII.ipynb` | Type II excitability with the resonant band-pass selector, threshold, criticality, bistability window and rate-input curves | Fig. 4 |
| `simulate_neuron_elliptic.ipynb` | Elliptic bursting with the resonant band-pass selector and a single slow state, compared side by side with the parabolic case | Fig. 5 |
| `simulate_neuron_typeIII.ipynb` | The subthreshold regime and its graded response. Outside the scope of the paper, kept as a pointer to future work | |

Figures 1 and 2 of the paper, together with the two block diagrams, are schematics and have no associated code.

The three notebooks that produce figures write them to a `figures/` folder, which is created on the first run.

## Launching the notebooks

To open JupyterNotebook or JupyterLab using Julia, execute:

```jl
using IJulia
notebook() # or jupyterlab()
```

Then browse to the `.ipynb` files to run them. If this is your first time launching Jupyter, Julia will prompt you to install it through Conda.

Most cells run in seconds. The exception is the rate-input sweep of `simulate_neuron_typeII.ipynb`, which runs one independent simulation per input value for four sigmoid gains and takes a few minutes.

## Author

Code written by Arthur Fyon.
