# Internal variables and constants

This document describes internal variables, constants, and intermediate quantities used within the SMEW_SS codebase. These variables are not intended to be modified by users and changing them may break model consistency.

---

## 1. Unit conversion constants

| Variable | Description |
|--------|-------------|
| `conv_mol` | Conversion factor between mmol_c-based soil chemistry units and mol-based model quantities. This is added because while solving numerical equations, some of the concentration would too low, hence we convert htem in micromols for the solver and convert them back in the main jupyter notenook to express them in mols.|

---

## 2. Chemical equilibrium constants

| Variable | Description |
|--------|-------------|
| `k_H` | Henry's law constant for CO₂ |
| `k_1` | First dissociation constant of carbonic acid |
| `k_2` | Second dissociation constant of carbonic acid |

---

## 3. Numerical and diagnostic variables

| Variable | Description |
|--------|-------------|
| `theta` | Intermediate soil moisture variable |
| `f_H` | Hydrogen ion fraction used in speciation |
| `f_Ca` | Calcium fraction on exchange sites |

---

## Warning

Users should not modify internal variables unless they are developing or extending the model. Changing internal constants or conversion factors will generally lead to physically inconsistent results.