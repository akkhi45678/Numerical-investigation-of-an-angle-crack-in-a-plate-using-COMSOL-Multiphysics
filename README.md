# Numerical Investigation of an Angle Crack in a Plate Using COMSOL Multiphysics

## Overview

This project presents a two-dimensional finite-element investigation of a rectangular plate containing a centrally embedded inclined crack. The analysis was performed in **COMSOL Multiphysics 6.3** using the Solid Mechanics interface and linear elastic fracture mechanics concepts.

The model investigates the influence of crack angle on the **J-integral**, **Mode-I stress intensity factor (KI)**, and **Mode-II stress intensity factor (KII)**.

The numerical model is based on the **NAFEMS angle-crack benchmark (R0020)**.

## Objectives

- Develop a finite-element model of an embedded angle crack in a tensile plate.
- Investigate the effect of crack orientation on fracture parameters.
- Calculate the J-integral at both crack tips.
- Evaluate normalized Mode-I and Mode-II stress intensity factors.
- Compare the numerical results with the NAFEMS benchmark values.

## Software

- **COMSOL Multiphysics 6.3**
- Solid Mechanics
- 2D stationary finite-element analysis

## Model Parameters

| Parameter | Value |
|---|---:|
| Plate width | 100 mm |
| Plate height | 125 mm |
| Crack length | 50 mm |
| Half crack length, `a` | 25 mm |
| Young's modulus | 207 GPa |
| Poisson's ratio | 0.30 |
| Applied tensile stress | 100 MPa |
| Crack angles | 90°, 67.5°, 22.5° |
| Normalization factor, `K0` | 28.025 MPa√m |

## Methodology

The plate is subjected to a uniform tensile load on the upper boundary. The bottom boundary is constrained against vertical displacement, while a horizontal displacement constraint is applied at the bottom-right corner to remove rigid-body motion.

A slit crack is introduced at the center of the plate. The crack orientation is varied parametrically.

The fracture response is evaluated using:

- J-integral
- Mode-I stress intensity factor, `KI`
- Mode-II stress intensity factor, `KII`

The crack-tip results are evaluated independently at the two crack tips.

## Results

### Normalized Stress Intensity Factors

| Crack angle | KI/K0 — Left | KI/K0 — Right | KII/K0 — Left | KII/K0 — Right |
|---:|---:|---:|---:|---:|
| 90° | 1.2057 | 1.2059 | 0.0119 | -0.0114 |
| 67.5° | 1.0281 | 1.0534 | 0.3772 | 0.3678 |
| 22.5° | 0.1856 | 0.1886 | 0.3943 | 0.4006 |

### Main observations

1. At **90°**, the crack is predominantly under Mode-I opening.
2. Reducing the crack angle introduces a significant Mode-II component.
3. At **22.5°**, Mode-II becomes more significant than Mode-I.
4. The numerical results show close agreement with the NAFEMS benchmark reference values.
5. Small differences between the two crack tips arise from the asymmetric constraint/loading arrangement.

## Results and Figures

### J-Integral

![J-integral results](Results/j_integral.png)

### Mode-I Stress Intensity Factor

![Mode-I SIF](Results/mode_I_sif.png)

### Mode-II Stress Intensity Factor

![Mode-II SIF](Results/mode_II_sif.png)

### COMSOL Model

![COMSOL model](Figures/model_geometry.png)

## Repository Structure

```text
Angle-Crack-Fracture-Analysis/
│
├── README.md
├── COMSOL_Model/
│   └── angle_crack_plate.mph
│
├── Report/
│   └── Angle_Crack_Plate_Project_Report.pdf
│
├── Results/
│   ├── j_integral.png
│   ├── mode_I_sif.png
│   └── mode_II_sif.png
│
└── Figures/
    └── model_geometry.png
```

## Conclusion

The COMSOL model successfully reproduces the expected mixed-mode fracture behavior of an inclined crack in a tensile plate. The results demonstrate a transition from predominantly Mode-I fracture at 90° toward stronger Mode-II behavior as the crack angle decreases.

The close agreement with the NAFEMS benchmark confirms that the numerical model provides a suitable reference case for studying linear elastic fracture mechanics and crack-tip parameters in COMSOL Multiphysics.

## Author

**Name:** ____Akhilesh yadav______________________  
**Institution:** _IIT KANPUR___________________  
**Department:** __Mechanical engineering___________________
