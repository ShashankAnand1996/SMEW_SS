# User-defined variables in `Example.ipynb`

This document describes the variables that users are expected to define or modify in `Example.ipynb` when running the model. These variables control the simulation setup, physical assumptions, and process representations. Minor differences in model parameters and outputs may arise if functions other than those used in `Example.ipynb` are selected.

Internal variables, output quantities, and plotting-related objects are not documented here.

---

## 1. Time discretization

These variables define the simulation length and temporal resolution.

| Variable | Description | Units |
|--------|-------------|-------|
| `t_end` | Total simulation duration | days |
| `dt` | Time step | days |
| `t` | Time vector derived from `t_end` and `dt` | days |

---

## 2. Soil parameters

Soil physical properties and initial soil moisture value.

| Variable | Description | Units |
|--------|-------------|-------|
| `soil` | Soil texture class (available options are 'sand', 'loamy sand', 'sandy loam', 'loam', 'clay loam', 'clay') | – |
| `Zr` | Root zone depth | m |
| `rho_bulk` | Bulk soil dry mass density | g m⁻³ |
| `s_in` | Initial relative soil moisture (fraction of soil pores filled with water, with value constrained between 0 and 1) | – |

---

## 3. Hydroclimatic parameters

### 3.1 Site characteristics

| Variable | Description | Units |
|--------|-------------|-------|
| `latitude` | Site latitude | radians |
| `altitude` | Site elevation | m |
| `albedo` | Surface albedo | – |
| `coastal` | Coastal correction flag. `True` if site is a coastal location, `False` if interior location | boolean |
| `day1` | Initial day of year | day |

---

### 3.2 Atmospheric forcing

| Variable | Description | Units |
|--------|-------------|-------|
| `wind` | Wind speed time series (same length as the time vector `t`) | m s⁻¹ |
| `temp_av` | Mean annual air temperature | °C |
| `temp_ampl_yr` | Amplitude of the annual (seasonal) cycle of daily mean air temperature, such that daily mean temperature varies sinusoidally between `temp_av ± temp_ampl_yr` over the year | °C |
| `temp_ampl_d` | Diurnal air temperature amplitude, defining the daily temperature range, with daily minimum and maximum temperatures given by `daily mean air temperature ± temp_ampl_d/2` | °C |

---

## 4. Rainfall parameters

Rainfall is generated stochastically using the following parameters.

| Variable | Description | Units |
|--------|-------------|-------|
| `R_tot` | Total annual rainfall | m yr⁻¹ |
| `lamda` | Mean rainfall event frequency (number of rainy days divided by total number of days) | d⁻¹ |
| `alfa` | Mean rainfall depth per event (average daily rainfall amount) | m |

---

## 5. Vegetation parameters

Parameters controlling vegetation growth and root properties.

| Variable | Description | Units |
|--------|-------------|-------|
| `T_v` | Vegetation growth time scale, i.e., the time it takes to reach its carrying capacity | days |
| `k_v` | Vegetation carrying capacity | g m⁻² |
| `v_in` | Initial vegetation biomass | g m⁻² |
| `t0_v` | Start day of vegetation growth | day |
| `RAI` | Root area index | m² m⁻² |
| `root_d` | Average root diameter | m |

---

## 6. Soil carbon parameters

Variables related to soil organic carbon and respiration partitioning.

| Variable | Description | Units |
|--------|-------------|-------|
| `ADD` | External litter carbon input rate | g OC m⁻² d⁻¹ |
| `CO2_air_in` | Initial CO2 concentration in soil air | mol-conv L⁻¹ |
| `ratio_aut_het` | Ratio of autotrophic to heterotrophic respiration | dimensionless |
| `SOC_perc` | Initial soil organic carbon fraction | % |
| `SOC_in` | Initial SOC concentration | g OC m⁻³ |

---

## 7. Cation exchange capacity and alkaline cations

| Variable | Description | Units |
|--------|-------------|-------|
| `CEC_tot` | Total cation exchange capacity | conv_mol (default = µmol) m⁻² |
|`f_Ca_in`| Ca cation exchangeable fraction | - |
|`f_Mg_in`| Mg cation exchangeable fraction | - |
|`f_K_in`| K cation exchangeable fraction | - |
|`f_Na_in`| Na cation exchangeable fraction | - |
|`f_Al_in`| Al cation exchangeable fraction | - |
|`f_H_in`| H cation exchangeable fraction | - |
|`f_CEC_in`| Array of all exchangeable fractions in the soil | - |

---


## 8. Initial Si and carbonate minerals

Initial chemical state of the soil system.

| Variable | Description | Units |
|--------|-------------|-------|
| `CaCO3_in` | Initial calcium carbonate content | conv_mol |
| `MgCO3_in` | Initial magnesium carbonate content | conv_mol |
| `Si_in` | Initial Si concentration | conv_mol m⁻³ |
---

## 9. Enhanced weathering and rock powder inputs

Parameters describing rock powder application and mineral properties.

| Variable | Description | Units |
|--------|-------------|-------|
| `M_rock_in` | Applied rock powder mass | g m⁻² |
| `mineral` | List of mineral phases included in the rock powder | – |
| `rock_f_in` | Mineral fraction vector | – |
| `diss_f` | Dissolution factor to account for inhibition/enhancement of EW rates in the soil | - |
| `d_in` | Array of rock powder diameter distribution bins, a single representative value for an absence of a rock powder distribution | m |
| `psd_perc_in` | Array of diameter class weights, with the sum of the array equal to 1 | % |
| `SSA_in` | Specific surface area (use `np.nan` for the model to compute it) | m² g⁻¹ |
| `t_app` | Day of rock application | day |

---

## 10. Model configuration flags

Keywords used to select model formulations and options.

| Variable | Description |
|--------|-------------|
| `keyword_wb` | Water balance formulation type. Value of 1 selects varying soil moisture dynamics driven by stochastic rainfall. Value of 0 keeps the soil moisture value constant for the simulated days, and computes infiltration/rainfall necessary to balance the evapotranspiration and leakage losses |
| `keyword_add` | Background loss handling for cations and anions. Value of 1 sets background inputs from rain, litterfall, and background weathering that balances the loss via leakage and passive plant uptake (average over a simulated period). Value of 0 presents the case of no background input |
| `keyword_ssa` | Specific surface area estimation method |

---

## Notes

- All variables listed above are defined explicitly in `Example.ipynb`.
- Concentrations refer to dissolved species in soil porewater unless otherwise stated.
- Seasonal rainfall options require multi-year simulations.
- Column-integrated quantities (e.g., CEC, total solute inventories) are expressed per unit ground area (m⁻²).
- Users are encouraged to modify only user-facing parameters unless they are familiar with the internal model structure.
