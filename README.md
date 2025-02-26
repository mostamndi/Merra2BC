# Merra2BC
Merra2BC is an interpolation utility, which creates for a WRF-Chem simulation initial and time-varying chemical boundary conditions (IC&BC) based on MERRA-2 reanalysis.

Merra2BC is written on Python and requires:
NetCDF4 interface to work with [netCDF](https://github.com/Unidata/netcdf4-python) files and [SciPy](https://github.com/scipy/scipy) interpolation package.


## Workflow

1. run *real.exe*, which will produce wrfinput and wrfbdy files
2. download required [MERRA-2](https://disc.gsfc.nasa.gov/daac-bin/FTPSubset2.pl) collections
3. run *git clone https://github.com/saneku/Merra2BC.git*
4. edit *config.py*
5. run *python zero_fields.py* to zero required fields (since utility will add values to the existing)
6. run *python main.py*
7. modify *namelist.input* file at section *&chem* (*have_bcs_chem = .true.* for BC *chem_in_opt = 1* for IC )
8. run *wrf.exe*
