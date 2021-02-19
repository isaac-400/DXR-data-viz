# Data Design/Implementation Specifications

Isaac Feldman, February 2021

## Data Source

GFS (Global Forecasting System) data contains variables for spatial weather data across the whole globe. We are interesting in the daily forecasts for wind speed a direction (ugrds and vgrds) at various heights above ground level which we can visualize with streamlines. GFS 1 degree data can be obtained for each day  with a forecast to the future from [NOMADS](https://nomads.ncep.noaa.gov/) via HTTP requests. 

## Data Flow

1. data is downloaded from NOMADS via HTTP is GRIB2 format. we request the GRIB2 data with the exact varibles we need
2. data is processed from GRIB2 to a more readable format like csv
	- current working pipline would use [pygrib](https://github.com/jswhit/pygrib) running in Unity's [python environment](https://docs.unity3d.com/Packages/com.unity.scripting.python@2.0/manual/index.html)
3. csv data is loaded into Unity to be used as a source for textures, particle system force fields, etc.
	- csv data can be loaded and (u,v) wind vector components can be loaded to a 3d texture for a particle force field.




