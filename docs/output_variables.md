# Model output variables

This document describes the primary output variables produced by the SMEW_SS model. These variables represent model states, fluxes, and diagnostic quantities that may be analyzed or visualized by users.

---

## 1. Air and soil temperature series
|--------|-------------|-------|
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
| `L` | Drainage / leakage flux | m d⁻¹ |
| `Q` | Runoff | m d⁻¹ |
| `Irr` | Irrigation input | m d⁻¹ |

---

## 3. Vegetation, organic carbon, and respiration outputs

| Variable | Description | Units |
|--------|-------------|-------|
| `v` | Vegetation biomass | g m⁻² |
| `SOC` | Soil organic carbon concentration time series | g OC m⁻³ |
| `r_het` | Heterotrophic respiration flux time series | mol-conv m⁻² d⁻¹ |
| `r_aut` | Autotrophic respiration flux time series | mol-conv m⁻² d⁻¹ |
| `D` | Soil gas diffusivity time series | m² d⁻¹ |

---

## 4. Soil water alkaline cations

| Variable | Description | Units |
|--------|-------------|-------|
| `conc_in` | Array of dissolved cation concentrations in soilpore water, with the same size and ordering as `f_CEC_in` | conv_mol (default = µmol) m⁻³ |
|`K_CEC`| Array of Gaines–Thomas selectivity coefficients governing equilibrium partitioning between adsorbed and dissolved cations | - |

---


## 6. Comprehensive solver output (`data` dictionary obtained from the `biogeochem_balance` function)

In addition to the primary output variables listed above, the biogeochemical solver returns a dictionary named `data` containing all time-dependent state variables, fluxes, and intermediate diagnostic quantities used internally by the model.

This dictionary includes, but is not limited to, the following categories of variables:

### Chemical state variables
Time series of dissolved and adsorbed species, including:
- Major cations (Ca, Mg, K, Na) in solution and on exchange sites
- Aluminum species and hydrolysis products
- Carbonate system components (CO₂, HCO₃⁻, CO₃²⁻)
- Alkalinity and dissolved inorganic carbon

### Total inventories
Column-integrated pools combining dissolved and adsorbed phases, such as:
- Total cation inventories
- Total alkalinity
- Total inorganic carbon
- Total silicon and aluminum

### Weathering and mineral properties
Variables describing enhanced weathering dynamics, including:
- Mineral-specific weathering rates
- Reactive surface area
- Particle size distribution and evolution
- Remaining rock and mineral masses


### Numerical and solver diagnostics
Residuals of the nonlinear solver

## 7. Notes

- Fluxes are expressed per unit ground area unless otherwise stated.
- Time series outputs have the same length as the model time vector.
