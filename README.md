# Mathematical Modeling

Population and social dynamics models developed in Python as part of a Mathematical Modeling course at the Institute of Science Tokyo. The notebooks cover ecological models, spatial lattice models, and agent-based models of collective behavior.

## Overview

This repository contains notebooks originally developed for coursework and later cleaned up for public sharing. The original problem statements have been paraphrased, and each notebook includes the model setup, derivation where needed, Python implementation, and a short discussion of the results. The amount of original and adapted work differs between notebooks, with more details provided in the Attribution section.

The notebooks are divided into two main groups:
- **Population dynamics** covers single-species growth, predator-prey systems, and spatial lattice models, including analytical methods such as equilibria, nullclines, and Jacobian stability, as well as numerical simulations.
- **Social dynamics** covers threshold models, cultural transmission, coordination games, and collective-action problems using game theory and agent-based models.

## Repository structure

```
Mathematical-Modeling/
├── README.md
├── LICENSE
├── requirements.txt
├── .gitignore
├── population-dynamics/
│   ├── 01_euler_rk_methods.ipynb
│   ├── 02_predation_pest_control.ipynb
│   ├── 03_lotka_volterra_model.ipynb
│   ├── 04_rosenzweig_macarthur_model.ipynb
│   └── 05_ecology_lattice.ipynb
└── social-dynamics/
    ├── 01_granovetter_threshold_model.ipynb
    ├── 02_cultural_evolution.ipynb
    ├── 03_social_interaction_models.ipynb
    └── 04_tragedy_of_the_commons.ipynb
```

## Contents

### Population & Ecological Dynamics (`/population-dynamics`)

| # | Notebook | Topic | Methods |
|---|----------|-------|---------|
| 01 | [Euler & Runge-Kutta Methods](population-dynamics/01_euler_rk_methods.ipynb) | Numerical integration accuracy on the logistic equation | Euler, RK4, comparison vs analytical solution |
| 02 | [Predation-Controlled Pest Density](population-dynamics/02_predation_pest_control.ipynb) | Equilibria of a pest population under predation | Analytical equilibria (Cardano's formula), Euler integration, stability classification |
| 03 | [Lotka-Volterra Model](population-dynamics/03_lotka_volterra_model.ipynb) | Classic predator-prey oscillations | Euler & RK4 integration, time-series and phase-space analysis |
| 04 | [Rosenzweig-MacArthur Model](population-dynamics/04_rosenzweig_macarthur_model.ipynb) | Predator-prey with logistic prey growth and saturating predation | Analytical equilibria, nullcline & Jacobian stability analysis, RK4 simulation |
| 05 | [Lattice-Based Ecological Model](population-dynamics/05_ecology_lattice.ipynb) | Spatial plant-herbivore-predator dynamics | Stochastic cellular automaton on a lattice with periodic boundaries |

### Social & Collective Dynamics (`/social-dynamics`)

| # | Notebook | Topic | Methods |
|---|----------|-------|---------|
| 01 | [Granovetter's Threshold Model](social-dynamics/01_granovetter_threshold_model.ipynb) | Threshold-driven adoption and tipping points | Mean-field model vs. agent-based simulation; uniform & normal thresholds |
| 02 | [Cultural Evolution](social-dynamics/02_cultural_evolution.ipynb) | Unbiased vs. biased cultural transmission, drift and finite-size effects | Agent-based simulation, multi-trial averaging, parameter sweeps |
| 03 | [Coordination Games & Q-Learning](social-dynamics/03_social_interaction_models.ipynb) | The escalator game: reaching equilibrium through learning | Analytical Nash equilibria (pure & mixed), independent Q-learning |
| 04 | [Tragedy of the Commons](social-dynamics/04_tragedy_of_the_commons.ipynb) | Human harvesting decisions coupled to a shared ecological resource | Original agent-based model; Granovetter vs. Q-learning decision rules on a lattice |

## Concepts & tools demonstrated

- **Population dynamics:** logistic and predator-prey ODE systems, equilibria and Cardano's formula, nullcline and Jacobian stability analysis, spatial/lattice ecological models
- **Social dynamics:** threshold models and tipping points, cultural transmission (drift vs. selection), coordination games and Nash equilibria, reinforcement learning (Q-learning), collective-action problems
- **Modeling approaches:** analytical (mean-field) models compared against agent-based simulations, finite-size and mean-field limit effects
- **Numerical methods:** Euler's method, Runge-Kutta (RK4) integration, stochastic cellular automata
- **Python:** NumPy, SciPy, Matplotlib

## Running locally

```bash
git clone https://github.com/Z0Narf/Mathematical-Modeling.git
cd Mathematical-Modeling
pip install -r requirements.txt
jupyter notebook
```

The plots are pre-rendered in the notebooks, so everything is viewable on GitHub without running anything.

## Attribution

These notebooks were originally developed for coursework, so the amount of original work differs between them. The main contributions for each notebook are described below.

- **Population dynamics** is largely my own work:

    - **ODE models (01-04):** Numerical integration code was written for my ODE coursework using Euler's method and RK4, then applied to the model equations here. The equilibrium and stability derivations are also my own work.
    - **Lattice model (05):** The model is based on a provided plant-rabbit model, which I modified by adding predator (fox) pursuit and herbivore (rabbit) evasion behavior.

- **Social dynamics** includes both provided and original work:

    - **01 (Granovetter):** The agent-based simulation was provided. I derived the analytical mean-field model and compared its results with the ABM.
    - **02 (Cultural Evolution):** The notebook is based on a provided ABM. My contribution includes the parameter variations, multi-trial averaging, additional cases, and analysis.
    - **03 (Escalator Game):** The Q-learning simulation code was provided. I derived the pure and mixed Nash equilibria analytically.
    - **04 (Tragedy of the Commons):** The model structure and program flow were specified in the course. The implementation follows this structure while adapting my lattice-ecology code and the human decision-making methods introduced in class.

Problem statements are paraphrased from course material. Notebooks that build on provided code note this in the code itself.

## License

Code and write-ups in this repository are shared under the MIT License ([LICENSE](LICENSE)). Problem statements are paraphrased from course material and belong to the original instructors.
