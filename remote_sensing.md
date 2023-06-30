# Remote sensing

Bestilling: Nansen senter for fjernmåling

## Coverage
Everything that mentions remote sensing in any capacity/context. Focus on Norwegian research. 

## Search string, WoS

Without agencies string: 5475 (2012-2022) - https://www.webofscience.com/wos/woscc/summary/44e3fae1-db54-4c70-ba0b-eccae9ef8d3b-94c33908/relevance/1 

Note that there are citation mesos and WOS categories for Remote sensing:
* https://www.webofscience.com/wos/woscc/summary/17287e55-10ee-4de9-baac-591c9981d5ec-94b5f766/relevance/1 (669 - 94 not found)
* https://www.webofscience.com/wos/woscc/summary/6ba93a63-c594-4f74-a36a-68e69080170c-94eaaaa3/relevance/1 (874 - 189 not found)

There are also journals - these contain 465 results for Norway (47 not found by our search string)

```py
(CU="norway") 
AND 
SO = 
(EARTH OBSERVATION "AND" REMOTE SENSING 
OR EUROPEAN JOURNAL OF REMOTE SENSING 
OR GISCIENCE REMOTE SENSING 
OR INTERNATIONAL JOURNAL OF REMOTE SENSING 
OR JOURNAL OF APPLIED REMOTE SENSING 
OR REMOTE SENSING 
OR REMOTE SENSING OF ENVIRONMENT
)
```

### General terms

Issue: "GIS" can be used in other contexts, e.g. genome islands, greenland ice sheet, gas-insulated switchgear. However, it is often used in abstracts without being written out in full...(https://www.webofscience.com/wos/woscc/summary/a45d20d7-f37d-4ef5-b20e-b799df5de0e3-94b47eee/relevance/1)

* Added `PPGIS`- public participation GIS
* Added `"aerial photograph*"`
* Added `"aerial laser scan*"`
* Added `remotely sensed`
* Added `unmanned aerial system*` and `unoccupied aerial vehicle$`
* Added `satellite data`

```py
TS=
(   "remote sensing" OR "remotely sensed" OR "earth observation"
    OR "geographical information system*" OR "geographic information system*" OR "PPGIS"
    OR "airborne laser scan*" OR "aerial laser scan*"
    OR "ground truthing" OR "ground validat*"
    OR "GIScience"
    OR "aerial photograph*"
    OR "satellite data"
    OR
    (
        ("satellite$" 
        OR "drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" OR "UAV" OR "UAVs"
        OR "GIS"
        )
        AND
            ("mapping" OR "mapped" OR "ground measure*" OR "monitor*" OR "sentinel" 
            OR "imaging" OR "image$" OR "imagery"
            OR "optical" OR "radar" OR "sensor$"
            )
    )
)
```

Additional terms to be combined with GIS (not covered above or in later phrases):

```py
TS=
(   "GIS"
    AND
        ("satellite$" 
        OR "drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" OR "UAV" OR "UAVs"
        OR "spatial" OR "geographic*" OR "topograph*" OR "elevation"
        OR "land cover"
        OR "map" OR "maps" OR "mapping" OR "mapped" 
        OR "travel" OR "roads" OR "transport"
        OR "GIS based" OR "GIS approach" OR "GIS method$" OR "GIS tool$" OR "GIS software" OR "GIS database$"
        )
)
```


### Agencies

Difficult as a number of physics papers? Have dropped `satellit*"`, `monitor*`, `optical` and `sensor$` from the second phrase to try and help. I actually suspect that those found by this phrase (and this phrase alone, not the others) are not particularly relevant - check. A lot of space/astrophysics?

```py
TS=
(
    ("European space agency"
    OR "national aeronautics and space administration"
    OR "Japan Aerospace Exploration Agency" 
    OR "National Oceanic and Atmospheric Administration"
    OR "Indian Space Research Organization"
    OR "China National Space Administration"
    OR "Centre National D’Etudes Spatiales" OR "French Space Agency"
    OR "European Organization for the Exploration of Meteorological Satellites"
    OR "German Aerospace Centre"
    OR "ESA" OR "NASA" OR "JAXA" OR "NOAA" OR "ISRO" OR "CNSA" OR "CNES" OR "EUMETSAT" OR "DLR"
    )
    AND 
        ("drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" OR "UAV" OR "UAVs" 
        OR "GIS" OR "spatial" OR "geographic*" OR "topograph*" OR "elevation"
        OR "map" OR "maps" OR "mapping" OR "mapped" 
        OR "ground measure*" OR "sentinel" 
        OR "imaging" OR "image$" OR "imagery"
        OR "radar"
        OR "Change Detection" OR "Image Classification" OR "land cover" OR "land classification"
        )
)
```

### Satellite missions

Combined those assumed to be more ambiguous with remote sensing terms. Note that the ambiguous terms are not combined with `"remote sensing" OR "earth observation" OR "geographical information system*" OR "GIS" OR "GIScience"` because there is no point - these will be found by phrase 1 anyway.

* Added `TanDEM-X`

```py
TS=
(
    ("ERS1&2" OR "ERS-1" OR "ERS1" 
    OR "ENVISAT" OR "Cryosat"
    OR "Sentinel-1" OR "Sentinel-2" OR "Sentinel-3" OR "Sentinel-4" OR "Sentinel-5" OR "Sentinel-6 (Michael Freilich)" 
    OR "MetOp" OR "Landsat" 
    OR "RADARSAT" OR "SeaWIFS" OR "TerraSAR-X" OR "AMSR2" OR "ICESat" OR "QuickSCAT" OR "QuikSCAT" 
    OR "SCATSat" OR "CFOSAT" OR "OceanSAT" OR "CloudSat" OR "KOMPSAT" OR "Meteosat" 
    OR "COSMO-SkyMed" OR "TerraSAR-X" OR "TanDEM-X" OR "Topex Poseidon" 
    OR "EarthExplorer-10" OR "EarthExlorer-11" 
    OR "EU copernicus service*"
    )
    OR
    (
        ("Terra" OR "Aqua" OR "NOAA" 
        OR "ALOS" OR "GOCE" OR "GRACE" OR "CFOSAT" OR "SRAL" OR "HY-2"
        OR "DMSP" OR "Coriolis*" OR "MSG" OR "SNPP" OR "GCOM" OR "CALIPSO"  
        OR "GOES" OR "GOSAT" OR "Jason" OR "MSG" OR "NIMBUS" 
        OR "OCO" OR "PROBA" OR "TOMS" OR "RapidEye" OR "SAGE" 
        OR "Aeolus" OR "Biomass" OR "EarthCARE" OR "FLEX" OR "SMAP" OR "SMOS" OR "SPOT" OR "Suomi" 
        OR "Swarm" OR "SWOT" OR "TanDEM" OR "TRMM" 
        OR "CHIME" OR "CRISTAL" OR "ROSE-L" 
        OR "LSTM" OR "CIMR" OR "CO2M" OR "MTG" OR "ALTIUS"
        )
        AND 
            ("satellit*" 
            OR "drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" 
            OR "GIS" OR "spatial" OR "geographic*" OR "topograph*" OR "elevation"
            OR "map" OR "maps" OR "mapping" OR "mapped" 
            OR "ground measure*" OR "sentinel" 
            OR "imaging" OR "image$" OR "imagery"
            OR "optical" OR "radar" OR "sensor$"
            OR "Change Detection" OR "Image Classification" OR "land cover" OR "land classification"
            )
    )
)
```

### Satellite sensors

Combined those assumed to be more ambiguous with remote sensing terms. `spectrometry` must be combined due to "mass spectrometry"

* Added `Spectroradiometer`

```py
TS=
(
    ("Synthetic Aperture Radar" OR "Along Track Scanning Radiomet*" OR "Radar Altimet*" OR "Microwave Radiomet*" 
    OR "Wind Scatteromet*" OR "Advanced Synthetic Aperture Radar" OR "Medium Resolution Imaging Spectromet*" OR "Multispectral Instrument*" 
    OR "Land Colo$r Instrument*" OR "Ocean Colo$r Instrument*" R "Land Surface Temperature Radiomet*" OR "Sea Surface Temperature Radiomet*" 
    OR "Synthetic Aperture Radar Altimet*" 
    OR "UVN Spectromet*" 
    OR "radiometry" OR "TIR radiomet*" OR "Advanced Very High Resolution Radiomet*" OR "infrared radiomet*" OR "microwave radiomet*" 
    OR "spectroradiomet*"
    OR "scatteromet*" OR "gravimet*" OR "Lidar altimet*" OR "hyperspectral" OR "GNSS Altimet*" 
    )
    OR
    (
        ("SAR" OR "ATSR" OR "RA" OR "MWR" OR "WSC" OR "ASAR" OR "MERIS" OR "MSI" 
        OR "OLCI" OR "SLSTR" OR "SRAL" OR "UVN" OR "TIR" OR "AVHRR" OR "NIR-HSI"
        OR "spectrometry" OR "spectrometer" 
        )
        AND
            ("satellit*" 
            OR "drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" OR "UAV" OR "UAVs" 
            OR "GIS"
            OR "spatial" OR "geographic*" OR "topograph*" OR "elevation"
            OR "map" OR "maps" OR "mapping" OR "mapped" 
            OR "ground measure*" OR "sentinel" 
            OR "optical" OR "radar" 
            OR "Change Detection" OR "Image Classification" OR "land cover" OR "land classification"
            )
    ) 
)
```

### Satellite methods

Combined those assumed to be more ambiguous with remote sensing terms. 

```py
TS=
(
    ("interferometry" OR "ocean colour" OR "ocean color" OR "InSAR" 
    OR "Atmospheric Correction" OR "Radiometric Calibration" 
    OR "Geospatial Analysis"
    )
    OR
    (
        ("Change Detection" OR "Image Classification" 
        OR "Data Fusion" OR "Image Fusion" OR "Feature Extraction" 
        OR "Time-Series Analysis" 
        OR "land classification"
        )
        AND
            ("satellit*" 
            OR "drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" OR "UAV" OR "UAVs" 
            OR "GIS" OR "spatial" OR "geographic*" OR "topograph*" OR "elevation"
            OR "land cover"
            OR "map" OR "maps" OR "mapping" OR "mapped" 
            OR "ground measure*" OR "sentinel" 
            OR "optical" OR "radar"
            )
    )
)
```

### Results/outputs

```py
TS=
(
    ("Digital elevation model" OR "DTM" 
    OR "Doppler" OR "SAR" 
    OR "Vegetation Indices" OR "Vegetation index" 
    OR "Bathymetr*" OR "Ocean Colo$r" OR "Chlorophyll-a Concentration" 
    OR "Sea Surface Salinity" OR "SSS" OR "Sea Surface Height" OR "SSH" OR "Sea surface temperature" OR "SST" 
    OR "Ocean Surface Winds" OR "Ocean Surface Currents" OR "Ocean Surface Waves" OR "Ocean Heat Content" 
    OR "Sea Ice Concentration" OR "Sea Ice Extent" OR "Sea Ice Thickness" OR "Sea Ice Motion" OR "Iceberg Detection" OR "Ice Type Classification" 
    OR "oil spill detection"
    )
    AND
        ("satellit*" 
        OR "drone$" OR "unmanned aerial vehicle$" OR "unmanned air vehicle$" OR "unmanned aerial system$" OR "unoccupied aerial vehicle$" OR "UAV" OR "UAVs" 
        OR "GIS"
        OR "map" OR "maps" OR "mapping" OR "mapped" 
        OR "ground measure*" OR "sentinel" 
        OR "imaging" OR "image$" OR "imagery"
        OR "optical" OR "radar" OR "sensor$"
        OR "Change Detection" OR "Image Classification" OR "land cover" OR "land classification"
        )
)
```


## Norwegian terms

* jord observasjon
* jordobservasjon
* fjernmåling
* fjernsansing
