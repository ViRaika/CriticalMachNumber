# Critical Mach Number Calculator (MATLAB)

## Prandtl–Glauert Transformation and Compressible Flow

### Overview

This repository contains a MATLAB-based tool to compute the **critical Mach number (M_crit)** for airfoils using classical compressible flow theory. The method applies the **Prandtl–Glauert compressibility correction** to incompressible pressure coefficient data and equates it to the **sonic pressure coefficient** from isentropic flow relations.

The tool is designed for subsonic and transonic aerodynamic analysis and is useful for early-stage aircraft design studies.

### Features

- Computes critical Mach number using MATLAB `fzero`
- Uses incompressible minimum pressure coefficient as input
- Supports symmetric airfoils (e.g., NACA 0012)
- Includes plotting utilities for Cp distributions

---

## Theory

### Prandtl–Glauert Transformation

The Prandtl–Glauert rule corrects incompressible pressure coefficients for subsonic compressibility:

$C_{p, \text{comp}} = \frac{C_{p, \text{inc}}}{\sqrt{1 - M^2}}$


Valid for subsonic, inviscid, irrotational flow conditions.

---

### Sonic Pressure Coefficient for Compressible Flow

At the critical condition, local flow first becomes sonic.  
The pressure coefficient at sonic conditions is:

$C_p^* = \frac{2}{\gamma M^2} \left[ \left( \frac{2 + (\gamma - 1) M^2}{\gamma + 1} \right)^{\gamma / (\gamma - 1)} - 1 \right]$


Where:

- gamma = 1.4 (air)

---

### Critical Mach Number Equation

The critical Mach number is obtained by solving:

$\frac{C_{p0, \text{min}}}{\sqrt{1 - M_{\text{crit}}^2}} = \frac{2}{\gamma M_{\text{crit}}^2} \left[ \left( \frac{2 + (\gamma - 1) M_{\text{crit}}^2}{\gamma + 1} \right)^{\gamma / (\gamma - 1)} - 1 \right]$


This nonlinear equation is solved numerically using MATLAB’s `fzero`.

---
