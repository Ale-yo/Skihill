# Finite Element Analysis of the 2026 Olympic Ski Jump

Finite Element Analysis (FEA) and dynamic investigation of a two-dimensional planar frame idealization of the ski-jumping hill for the **Milano–Cortina 2026 Winter Olympic Games**, developed for the *Advanced Dynamics of Mechanical Systems* course at **Politecnico di Milano** (A.Y. 2025/2026).

## Project Overview
The project models the ski-jumping track as composed of a straight segment followed by a circular arc, supported by two steel lattice frameworks and constrained in an extremity point by a linear spring.

The study covers:
- **FE Model Definition:** Discretization within the $0\text{–}6\text{ Hz}$ frequency range ($\Omega_{\max} = 6\text{ Hz}$, safety factor $\eta = 1.5$) using element length limits based on pinned-pinned beam theory.
- **Modal Analysis:** Assembly of global mass and stiffness matrices (including the lumped spring contribution) and extraction of the first four natural frequencies and mode shapes.
- **Frequency Response Functions (FRFs):** Evaluation of FRF magnitude and phase using both the full FEM formulation and modal approach.
- **Static Response:** Deflection analysis under distributed snow load along the sliding track.
- **Moving Load Dynamics:** Time-domain simulation of a $90\text{ kg}$ skier descending the ramp using equivalent nodal forces/moments and modal integration via `ode45`.

## Repository Structure
- `scripts/` — MATLAB scripts and functions for model setup (`loadstructure`, `dis_stru`), matrix assembly (`assem`), modal/FRF/static/moving-load analyses, and plotting (`diseg2`).
- `codes/` — Project report (`Skihill.pdf`).
- `LICENSE` — Project license (`MIT`).

## Usage
1. Clone the repository.
2. Open **MATLAB** and add the `codes/` folder to the path.
3. Run `scom.m` (or the relevant analysis scripts) to generate the FE model, eigenmodes, FRFs, static deflection, and moving-load response.
4. Refer to [`pdf/Skihill.pdf`](pdf/Skihill.pdf) for full equations, assumptions, and discussion.
