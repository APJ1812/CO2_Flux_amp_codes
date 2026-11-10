### CO2_Flux_amp_codes

## Citation

# Joshi, A. P., Chakraborty, K., Sarma, V. V. S. S., Ghoshal, P. K., Sridevi, B., & Lachkar, Z. (2026). Climate Change Induced Seasonal Amplification of the Indian Ocean CO2 Sink. *Geophysical Research Letters*, 53(19), e2026GL123472. https://doi.org/10.1029/2026GL123472

## Creators

### Dr Apurva Padamnabh Joshi (A. P. Joshi), Kunal Chakraborty, V. V. S. S. Sarma, Prasanna Kanti Ghoshal, B. Sridevi, and Zouhair Lachkar

This repository contains Jupyter notebooks for reproducing the analysis and figures presented in the above paper. The codes calculate air–sea CO2 fluxes, examine long-term changes in seasonal CO2-flux and surface pCO2 amplitudes, and investigate the contributions of the main drivers of flux seasonality across the Indian Ocean.

## Repository Structure

The repository includes the following notebooks:

1. **`Flux_analysis_direct_cal.ipynb`**
   - Calculates air–sea CO2 flux using surface ocean pCO2, atmospheric pCO2, sea surface temperature (SST), sea surface salinity (SSS), and wind speed.
   - Examines the seasonal cycle and long-term/interannual changes in CO2-flux amplitude across the Arabian Sea (AS), Bay of Bengal (BoB), Equatorial Indian Ocean (EIO), and Southern Indian Ocean (SIO).
   - Includes polynomial-harmonic smoothing and regional statistical analyses.

2. **`Flux_seas_amp_drivers_direct_cal.ipynb`**
   - Compares the seasonal CO2-flux cycles for 1980–1989 and 2010–2019.
   - Quantifies the contributions of SST, SSS, wind speed, and the sea–air pCO2 difference (ΔpCO2) to seasonal CO2-flux variability and changes between the two decades.
   - Generates regional analyses and figures for the Indian Ocean subregions.

3. **`pco2_seas_timeseries.ipynb`**
   - Examines the long-term evolution of surface pCO2 seasonal amplitude.
   - Applies a locally fitted polynomial-harmonic model to estimate yearly seasonal amplitudes.
   - Compares seasonal pCO2 variability between 1980–1989 and 2010–2019, including thermal and non-thermal components, across the Indian Ocean regions and selected subregions.

## Input Data

The notebooks require external NetCDF files. These data files are not included in this repository and must be obtained separately.

The notebooks refer to the following input files:

- **`pCO2-Corrected_INCOIS-BIO-ROMS.nc`** – Surface ocean pCO2 and associated variables. The notebooks access variables including `pCO2_Clim`, `Deviant_uncertainty`, `SST`, and `SSS`.
- **`pCO2_atm_gridded_1deg.nc`** – Gridded atmospheric pCO2 (`pCO2_atm`).
- **`JRA_WS_second_moment_following_Fay_et_al.nc`** – Wind-speed fields (`ws` and `ws_std`) used to derive the wind-speed second moment in the flux calculations.

Place the files in the locations expected by the notebooks, or edit the file paths in the data-loading cells. In particular, `Flux_analysis_direct_cal.ipynb` and `Flux_seas_amp_drivers_direct_cal.ipynb` use relative paths beginning with `../` for some input files, whereas `pco2_seas_timeseries.ipynb` loads the surface pCO2 file from the notebook's current working directory.

Check that the input datasets contain the required variables and compatible time, latitude, and longitude coordinates before running the analyses.

## Requirements

The scripts require Python 3.7 or later and Jupyter Notebook/JupyterLab. Install the necessary dependencies using:

```bash
pip install numpy pandas matplotlib scipy xarray xskillscore basemap
```

### Key Libraries

- `numpy`
- `pandas`
- `matplotlib`
- `scipy`
- `xarray`
- `xskillscore`
- `Basemap`

## Usage

Clone or download this repository and open the notebooks in Jupyter Notebook or JupyterLab. Before execution, make sure that all required input NetCDF files are available and that the paths in the notebooks point to their locations.

### Flux Analysis

To calculate air–sea CO2 fluxes and examine regional and long-term changes in flux amplitude, open `Flux_analysis_direct_cal.ipynb`.

Run the notebook:

```bash
jupyter notebook Flux_analysis_direct_cal.ipynb
```

### Seasonal Flux Amplitude Drivers

To examine the contributions of SST, SSS, wind speed, and ΔpCO2 to seasonal CO2-flux variability, open `Flux_seas_amp_drivers_direct_cal.ipynb`.

Run the notebook:

```bash
jupyter notebook Flux_seas_amp_drivers_direct_cal.ipynb
```

### Surface pCO2 Seasonal Timeseries

To calculate and compare the long-term evolution of surface pCO2 seasonal amplitude and its thermal/non-thermal components, open `pco2_seas_timeseries.ipynb`.

Run the notebook:

```bash
jupyter notebook pco2_seas_timeseries.ipynb
```

## Notes

- The analyses use the 1980–2019 surface pCO2 product described in the associated paper.
- The decadal comparisons in the notebooks use 1980–1989 and 2010–2019.
- Regional definitions and coordinate selections are implemented directly in the notebooks. Check these selections if adapting the codes to another dataset or grid.
- Figures are generated within the notebooks. Update or uncomment the relevant `savefig` commands if figures need to be exported to files.

## Reference

For details of the scientific background, datasets, methodology, and interpretation of the results, please refer to:

Joshi, A. P., Chakraborty, K., Sarma, V. V. S. S., Ghoshal, P. K., Sridevi, B., & Lachkar, Z. (2026). Climate Change Induced Seasonal Amplification of the Indian Ocean CO2 Sink. *Geophysical Research Letters*, 53(19), e2026GL123472. https://doi.org/10.1029/2026GL123472
