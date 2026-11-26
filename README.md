# Finite Element Analysis of the 2026 Olympic Ski Jump

Finite Element Analysis (FEA) and dynamic investigation of a two-dimensional planar frame idealization of the ski-jumping hill for the **Milano–Cortina 2026 Winter Olympic Games**, developed for the *Advanced Dynamics of Mechanical Systems* course at **Politecnico di Milano** (A.Y. 2025/2026).

## Project Overview
The project models the ski-jumping track—composed of a straight segment followed by a circular arc of radius $R = 112\text{ m}$—supported by two steel lattice frameworks and constrained at point **B** by a linear spring ($k = 5 \cdot 10^7\text{ N/m}$) with proportional damping ($[C] = \alpha[M] + \beta[K]$, $\alpha = 0.1\text{ s}^{-1}$, $\beta = 2.0 \cdot 10^{-4}\text{ s}$)[cite: 4].

The study covers:
- **FE Model Definition:** Discretization within the $0\text{–}6\text{ Hz}$ frequency range ($\Omega_{\max} = 6\text{ Hz}$, safety factor $\eta = 1.5$) using element length limits based on pinned-pinned beam theory ($55$ nodes, $153$ DOFs, $3$ materials, $65$ beam finite elements)[cite: 4, 6].
- **Modal Analysis:** Assembly of global mass and stiffness matrices (including the lumped spring contribution) and extraction of the first four natural frequencies and mode shapes ($1.57\text{ Hz}$, $2.97\text{ Hz}$, $4.91\text{ Hz}$, and $5.29\text{ Hz}$)[cite: 7].
- **Frequency Response Functions (FRFs):** Evaluation of FRF magnitude and phase using both the full FEM formulation and a reduced modal approach[cite: 10, 11].
- **Static Response:** Deflection under distributed snow load along the sliding track (maximum displacement of $0.174\text{ m}$)[cite: 11, 12].
- **Moving Load Dynamics:** Time-domain simulation of a $90\text{ kg}$ skier descending the ramp (initial speed $2\text{ m/s}$, constant accelerations of $3.5\text{ m/s}^2$ on the linear segment and $1.5\text{ m/s}^2$ on the curved segment) using equivalent nodal forces/moments and modal integration via `ode45`[cite: 12, 13, 14].

## Repository Structure
- `codes/` — MATLAB scripts and functions for model setup (`loadstructure`, `dis_stru`), matrix assembly (`assem`), modal/FRF/static/moving-load analyses, and plotting (`diseg2`), including `scom.m`.
- `pdf/` — Project report (`Skihill.pdf`)[cite: 1, 3].
- `LICENSE` — Project license (`MIT`)[cite: 1].

## Usage
1. Clone the repository.
2. Open **MATLAB** and add the `codes/` folder to the path.
3. Run `scom.m` (or the relevant analysis scripts) to generate the FE model, eigenmodes, FRFs, static deflection, and moving-load response.
4. Refer to [`pdf/Skihill.pdf`](pdf/Skihill.pdf) for full equations, assumptions, and discussion.
