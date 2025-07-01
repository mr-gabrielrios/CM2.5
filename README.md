### CM2.5 aquaplanet configuration

This repository contains necessary files for the aquaplanet configuration of CM2.5 (see [GFDL's website][https://www.gfdl.noaa.gov/cm2-5-and-flor/] for more details on CM2.5 and FLOR). The aquaplanet configuration can be initialized in both a fixed sea-surface temperature (SST) (i.e., "AMIP-style") or a slab-ocean configuration (for energetic consistency).

Contact Gabe Rios (gr7610@princeton.edu) for any questions related to model setup and configuration.

#### Notes for the aquaplanet setup:
- Modifications to the surface boundary condition (i.e., SSTs) can be made in `src/simple_coupler/ice_model.F90`. This includes custom SST configurations.
- The SWISHE configuration (Rios et al., 2025, Journal of Geophysical Research: Atmospheres) can be enabled from the namelist. For more details, please refer to the surface flux subroutines at `src/coupler/surface_flux.F90`.
- To cold-start, make sure no netCDF files with substring `fv_` are copied into the input directory (typically at relative path `work/INPUT` from the experiment path). Additionally, make sure a topography file containing coordinates `lat` and `lon` and variables `ftopo` and `htopo` are read in. 
