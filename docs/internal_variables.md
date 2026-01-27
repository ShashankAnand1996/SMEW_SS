# Internal variables and constants

This document describes internal variables, constants, and intermediate quantities used within the SMEW_SS codebase. These variables are not intended to be modified by users and changing them may break model consistency.

---

## 1. Unit conversion

| Variable | Description |
|--------|-------------|
| `conv_mol` | Unit conversion factor used to rescale molar concentrations to the internal units of the numerical solver (for example, from mol to µmol), in order to avoid numerical issues associated with very small concentrations; results are converted back to molar units for post-processing and reporting | 
| `conv_Al` | Unit conversion factor to change values for Al species in mols to nanomoles. This is added to ensure the stability of the numerical solver|

---

## 2. Constants for organic carbon calculations 

| Variable | Description |
|--------|-------------|
| `CO2_atm` | Atmospheric CO₂ concentration|

---

## 3. Chemical equilibrium constants

| Variable | Description |
|--------|-------------|
| `k_H` | Henry's law constant for CO₂ |
| `k_1` | First dissociation constant of carbonic acid |
| `k_2` | Second dissociation constant of carbonic acid |

---

## 4. Numerical and diagnostic variables

| Variable | Description |
|--------|-------------|
| `theta` | Intermediate soil moisture variable |
| `f_H` | Hydrogen ion fraction used in speciation |
| `f_Ca` | Calcium fraction on exchange sites |

---