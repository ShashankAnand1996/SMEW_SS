# SMEW_SS

SMEW_SS is an extension of the SMEW model for simulating enhanced weathering processes. It incorporates the effects of soil structure and the mixing of added rock powder particles.

## License

This repository builds upon the original SMEW model and is licensed under the Creative Commons Attribution–NonCommercial 4.0 International License (CC BY-NC 4.0). See `License.txt` for details.

## Repository structure

- `pyEW/`  
  Core ecohydrological and enhanced weathering model components.  
  Includes a new Python file `biogeochemSS.py` that provides a numerical solver to incorporate the effects of soil structure and mixing of added rock powder particles, following
  https://doi.org/10.1029/2025WR041479

- `Example.ipynb`  
  Example notebook demonstrating a typical SMEW model setup and run

- `Example_SS.ipynb`  
  Example demonstrating model runs with soil pore structure and rock powder mixing for a given particle size distribution (input data is in `Example_SS_Data` directory), using the new biogeochemical solver `biogeochem_balance_SS`

- `docs/`  
  Documentation for model inputs and example usage  
  - User-defined input variables: `docs/example_variables.md`
  - Model output variables: `docs/output_variables.md`
  - Internal variables and constants (developer reference): `docs/internal_variables.md`

## Getting started

1. Clone the repository
2. Install dependencies:

```bash
pip install -r requirements.txt
```

## Contact

Shashank Kumar Anand  
Email: shashankkumaranand@gmail.com

## Publication
 
Anand, S. K., Bertagni, M., Aburto, F., & Calabrese, S. (2026). Soil structure and mixing controls on water‐rock contact: Implications for Enhanced weathering. *Water Resources Research*, 62, e2025WR041479.
https://doi.org/10.1029/2025WR041479
