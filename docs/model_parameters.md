# User-defined variables in `Example.ipynb`

This document describes the variables that users are expected to define or modify in `Example.ipynb` when running the SMEW_SS model. These variables control the simulation setup, physical assumptions, and process representations.

Internal variables, derived quantities, and plotting-related objects are not documented here.

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

Soil physical properties and initial soil moisture.

| Variable | Description | Units |
|--------|-------------|-------|
| `soil` | Soil texture class (e.g., sand, loam, clay) | – |
| `Zr` | Root zone depth | m |
| `rho_bulk` | Bulk soil dry mass density | g m⁻³ |
| `s_in` | Initial relative soil moisture | – |

---

## 3. Hydroclimatic parameters

### 3.1 Site characteristics

| Variable | Description | Units |
|--------|-------------|-------|
| `latitude` | Site latitude | radians |
| `altitude` | Site elevation | m |
| `albedo` | Surface albedo | – |
| `coastal` | Coastal correction flag | boolean |
| `day1` | Initial day of year | day |

---

### 3.2 Atmospheric forcing

| Variable | Description | Units |
|--------|-------------|-------|
| `wind` | Wind speed time series | m s⁻¹ |
| `temp_av` | Mean annual air temperature | °C |
| `temp_ampl_yr` | Annual temperature amplitude | °C |
| `temp_ampl_d` | Daily temperature amplitude | °C |

---

## 4. Rainfall parameters

Rainfall is generated stochastically using the following parameters.

| Variable | Description | Units |
|--------|-------------|-------|
| `R_tot` | Total annual rainfall | m yr⁻¹ |
| `lamda` | Mean rainfall event frequency | d⁻¹ |
| `alfa` | Mean rainfall depth per event | m |

---

## 5. Vegetation parameters

Parameters controlling vegetation growth and root properties.

| Variable | Description | Units |
|--------|-------------|-------|
| `T_v` | Vegetation growth time scale | days |
| `k_v` | Vegetation carrying capacity | g m⁻² |
| `v_in` | Initial vegetation biomass | g m⁻² |
| `t0_v` | Start day of vegetation growth | day |
| `RAI` | Root area index | m² m⁻² |
| `root_d` | Mean root diameter | m |

---

## 6. Soil carbon parameters

Variables related to soil organic carbon and respiration partitioning.

| Variable | Description | Units |
|--------|-------------|-------|
| `SOC_perc` | Soil organic carbon fraction | % |
| `SOC_in` | Initial SOC concentration | g OC m⁻³ |
| `ADD` | External litter carbon input | g OC m⁻² d⁻¹ |
| `ratio_aut_het` | Autotrophic to heterotrophic respiration ratio | – |

---

## 7. Enhanced weathering and rock powder inputs

Parameters describing rock powder application and mineral properties.

| Variable | Description | Units |
|--------|-------------|-------|
| `M_rock_in` | Applied rock powder mass | g m⁻² |
| `rock_f_in` | Mineral fraction vector | – |
| `SSA_in` | Specific surface area (optional) | m² g⁻¹ |
| `t_app` | Day of rock application | day |

---

## 8. Initial solute and carbonate conditions

Initial chemical state of the soil system.

| Variable | Description | Units |
|--------|-------------|-------|
| `CaCO3_in` | Initial calcium carbonate content | mol |
| `MgCO3_in` | Initial magnesium carbonate content | mol |
| `Si_in` | Initial dissolved silica | mol |

---

## 9. Cation exchange capacity

| Variable | Description | Units |
|--------|-------------|-------|
| `CEC_tot` | Total cation exchange capacity | mol₍c₎ |

---

## 10. Model configuration flags

Keywords used to select model formulations and options.

| Variable | Description |
|--------|-------------|
| `keyword_wb` | Water balance formulation |
| `keyword_add` | Background loss handling |
| `keyword_ssa` | Specific surface area estimation method |

---

## Notes

- All variables listed above are defined explicitly in `Example.ipynb`.
- Seasonal rainfall options require multi-year simulations.
- Users are encouraged to modify only user-facing parameters unless they are familiar with the internal model structure.