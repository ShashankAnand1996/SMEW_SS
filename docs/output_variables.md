# Model output variables

This document describes the primary output variables produced by the SMEW_SS model. These variables represent model states, fluxes, and diagnostic quantities that may be analyzed or visualized by users.

---

## 1. Air and soil temperature series

| `temp_air` | Daily mean air temperature time series | °C |
| `temp_soil` | Soil temperature time series at depth `Zr` | °C |
| `temp_min` | Daily minimum air temperature | °C |
| `temp_max` | Daily maximum air temperature | °C |

---

## 2. Hydrological states and water fluxes

| Variable | Description | Units |
|--------|-------------|-------|
| `s` | Relative soil moisture | – |
| `n` | Soil porosity | – |
| `I` | Infiltration | m d⁻¹ |
| `E` | Soil evaporation | m d⁻¹ |
| `T` | Plant transpiration | m d⁻¹ |
| `L` | Drainage / leakage | m d⁻¹ |
| `Q` | Runoff | m d⁻¹ |
| `Irr` | Irrigation input | m d⁻¹ |

---

## 3. Vegetation outputs

| Variable | Description | Units |
|--------|-------------|-------|
| `v` | Vegetation biomass | g m⁻² |

---

## 4. Carbon fluxes

| Variable | Description | Units |
|--------|-------------|-------|
| `R_aut` | Autotrophic respiration | g C m⁻² d⁻¹ |
| `R_het` | Heterotrophic respiration | g C m⁻² d⁻¹ |
| `R_tot` | Total soil respiration | g C m⁻² d⁻¹ |

---

## 5. Enhanced weathering outputs

| Variable | Description | Units |
|--------|-------------|-------|
| `W_Ca` | Calcium weathering flux | mol m⁻² d⁻¹ |
| `W_Mg` | Magnesium weathering flux | mol m⁻² d⁻¹ |
| `HCO3` | Bicarbonate production | mol m⁻² d⁻¹ |