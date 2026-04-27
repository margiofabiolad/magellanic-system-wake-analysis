# Kinematic Analysis of the Magellanic System: SMC-LMC Host-Satellite Dynamics

## Overview

This project extends the kinematic analysis of the Magellanic System to study the
influence of the Small Magellanic Cloud (SMC) on the Large Magellanic Cloud (LMC),
treating the LMC as the host system. The analysis combines observational data from
the **Gaia DR3 survey** with N-body simulations, using coordinate transformations,
velocity field visualizations, and statistical comparisons of stellar populations.

This work was developed as part of doctoral research at IATE (UNC) and extends the
methodology of Garavito-Camargo et al. (2019) and Fushimi & Mosquera (2024)
to the SMC-LMC orbital frame.

---

## Scientific Context

The Large Magellanic Cloud (LMC) and Small Magellanic Cloud (SMC) form a bound
satellite system of the Milky Way. While most studies focus on the LMC's influence
on the MW halo, this project asks a different question:

> **Does the SMC produce a detectable kinematic signature in the stellar populations
> of the LMC, analogous to the dark matter wake induced by the LMC in the MW?**

To answer this, stellar tracers (globular clusters and RR Lyrae stars from Gaia DR3)
are analyzed in the **orbital reference frame of the SMC**, with the LMC as the host.
Stellar populations are classified into **Wake** and **Collective** components based
on their position relative to the SMC's orbit, and their mean velocity fields are
compared.

---

## What I Did

### 1. Coordinate Transformations
- Transformed Gaia DR3 observational coordinates (RA, Dec, distance, proper motions,
  radial velocity) into the **orbital reference frame of the SMC** using Astropy and Gala
- Defined a rotated coordinate system aligned with the SMC's past orbital trajectory
  around the LMC

### 2. Stellar Population Classification
- Classified stars into **Wake** and **Collective** populations based on their
  3D position relative to the SMC's orbital plane
- Applied radial cuts at 25–35 kpc from the LMC center

### 3. Velocity Field Visualizations
- **2D Quiver plots** in the SMC orbital plane showing mean velocity fields
  for Wake and Collective populations — adapted from Fushimi & Mosquera's
  original implementation to work in the SMC orbital frame
- **3D Quiver plots** showing the full 3D velocity structure
- **Mollweide projections** of stellar density and velocity fields using Healpy

### 4. Statistical Analysis
- **Welch's t-test** comparing mean velocities between Wake and Collective populations
- Density field computation and overdensity mapping (ρ/ρ_mean − 1)

---

## Results

### 2D Quiver: Velocity Fields in the SMC Orbital Plane

![Quiver SMC-LMC](wake_quiver-SMC-LMC.png)

*Velocity fields of Wake (red) and Collective (orange/green) stellar populations
in the orbital plane of the SMC, with the LMC as host. Points are colored by
overdensity ρ/ρ_mean − 1. The SMC position is marked by the black star; its
orbital velocity by the blue arrow. The pink line shows the past orbit of the SMC.*

> **Note:** Results are preliminary and under scientific validation as part of
> ongoing doctoral research.

---

## Technical Stack

| Tool | Purpose |
|---|---|
| `Python 3.10` | Core language |
| `Pandas` | Data manipulation (Gaia DR3 catalog) |
| `NumPy` | Vectorized computation |
| `Astropy` | Coordinate transformations, units |
| `Gala` | Galactic dynamics, orbit integration |
| `Galpy` | Gravitational potentials |
| `Healpy` | HEALPix maps, Mollweide projections |
| `Matplotlib` | All visualizations |
| `SciPy` | Statistical tests (Welch's t-test) |

---

## Data

- **Observational data**: Gaia DR3 survey — globular clusters and RR Lyrae stars
  in the Magellanic System. Publicly available at the
  [Gaia Archive](https://gea.esac.esa.int/archive/).
  The dataset was downloaded and pre-processed by Mercedes Mosquera and 
  Keiko Fushimi (Universidad Nacional de La Plata). 
  Raw data are not included in this repository.

---

## Acknowledgements

The 2D quiver plot implementation is based on code originally developed by
Mercedes Mosquera and postdoctoral researcher Keiko Fushimi (Universidad Nacional
de La Plata), who performed the kinematic analysis in the center of mass frame
of the Magellanic Clouds. I adapted their code to work in the orbital plane of
the SMC, using the LMC as the host system instead of the Galactic center.
Additional visualizations (Mollweide projections, 3D quiver plots) and the
statistical analysis of Wake vs Collective stellar populations were developed
independently as part of this work.

---

## References

- Fushimi, K. & Mosquera, M. et al. (2024). *A determination of the LMC dark matter
  subhalo mass using the MW halo stars in its gravitational wake*.
  [arXiv:2309.12989](https://arxiv.org/abs/2309.12989)

---

## Author

**Margionet Fabiola Díaz** — BSc in Physics, Universidad de Los Andes, Mérida, Venezuela  
[GitHub](https://github.com/margiofabiolad)

*This project was developed during my doctoral research in Astronomy at the
Instituto de Astronomía Teórica y Experimental (IATE), UNC, under the supervision
of Dr. Mariano Domínguez and co-supervision of Dr. Mercedes Mosquera
(Universidad Nacional de La Plata).*
