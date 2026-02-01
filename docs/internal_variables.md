# Internal variables and constants

This document describes internal variables, constants, and intermediate quantities that are visible in `Example.ipynb`. These variables are not intended to be modified by users and changing them may break model consistency.

---

## 1. Unit conversion

| Variable | Description |
|--------|-------------|
| `conv_mol` | Unit conversion factor used to rescale all molar and charge-equivalent quantities (e.g., mol → µmol) to improve numerical stability; all governing equations are solved in the scaled units and converted back to molar units for output |
| `conv_Al` | Similar to `conv_mol`, Unit conversion factor applied to aluminum species to improve numerical conditioning of Al speciation and cation-exchange equations; used to rescale Al-related variables to avoid stiffness at low concentrations |

---

## 2. Constants for organic carbon calculations 

| Variable | Description |
|--------|-------------|
| `CO2_atm` | Atmospheric CO₂ concentration|

---
