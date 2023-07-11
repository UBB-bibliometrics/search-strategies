# Remote sensing

Bestilling: Nansen senter for fjernmåling

## Scope

Everything that mentions remote sensing in any capacity/context. Focus on Norwegian research (i.e. publications where a Norwegian address is given as an affiliation). 

Timespan: Publication date = 2012-01-01 to 2022-12-31

## Search string, Web of Science

The following strings are combined together with OR (except from the agencies string). They are then combined with AND with `CU="Norway"` to filter for Norwegian publications. Carried out 11th July 2023. 

Carried out in the Web of Science Core Collection:
- WOS.SCI: 1945 to 2023
- WOS.AHCI: 1975 to 2023
- WOS.ESCI: 2018 to 2023
- WOS.SSCI: 1956 to 2023

Without agencies string: 6027 results (2012-2022) - https://www.webofscience.com/wos/woscc/summary/2acdd66e-e63f-4383-9372-8d76b2d129c4-9728ce92/relevance/1

### Journal search

Included content from journals about remote sensing. This was done via a search for journals including "remote sensing", "earth observation" or "GIS" int he title. Only those where the topic was perceieved to be exclusive were added (i.e. *IEEE Geosciences and Remote Sensing* was not included as geosciences seemed too broad and would result in articles from other fields being added).

```py
SO = 
(EARTH OBSERVATION "AND" REMOTE SENSING 
OR IEEE JOURNAL OF SELECTED TOPICS IN APPLIED EARTH OBSERVATIONS "AND" REMOTE SENSING 
OR INTERNATIONAL JOURNAL OF APPLIED EARTH OBSERVATION "AND" GEOINFORMATION 
OR GISCIENCE REMOTE SENSING OR TRANSACTIONS IN GIS OR ADVANCES IN REMOTE SENSING OF THE ATMOSPHERE FROM SPACE "AND" FROM THE GROUND 
OR ADVANCES IN REMOTE SENSING OF THE MIDDLE "AND" UPPER ATMOSPHERE "AND" THE IONOSPHERE 
OR ATMOSPHERIC REMOTE SENSING EARTH S SURFACE TROPOSPHERE STRATOSPHERE "AND" MESOSPHERE I 
OR ATMOSPHERIC REMOTE SENSING EARTH S SURFACE TROPOSPHERE STRATOSPHERE "AND" MESOSPHERE II 
OR CANADIAN JOURNAL OF REMOTE SENSING 
OR EGYPTIAN JOURNAL OF REMOTE SENSING "AND" SPACE SCIENCES 
OR EUROPEAN JOURNAL OF REMOTE SENSING 
OR INTERNATIONAL JOURNAL OF REMOTE SENSING 
OR ISPRS JOURNAL OF PHOTOGRAMMETRY "AND" REMOTE SENSING 
OR ITALIAN JOURNAL OF REMOTE SENSING RIVISTA ITALIANA DI TELERILEVAMENTO 
OR JOURNAL OF APPLIED REMOTE SENSING 
OR JOURNAL OF THE INDIAN SOCIETY OF REMOTE SENSING 
OR KOREAN JOURNAL OF REMOTE SENSING 
OR LAND SURFACE CHARACTERIZATION "AND" REMOTE SENSING OF OCEAN PROCESSES 
OR MIDDLE "AND" UPPER ATMOSPHERES SMALL SCALE STRUCTURES "AND" REMOTE SENSING 
OR NATURAL HAZARDS MONITORING "AND" ASSESSMENT USING REMOTE SENSING TECHNIQUE 
OR PFG JOURNAL OF PHOTOGRAMMETRY REMOTE SENSING "AND" GEOINFORMATION SCIENCE 
OR PHOTOGRAMMETRIC ENGINEERING "AND" REMOTE SENSING 
OR PHOTONIRVACHAK JOURNAL OF THE INDIAN SOCIETY OF REMOTE SENSING 
OR REMOTE SENSING 
OR REMOTE SENSING "AND" APPLICATIONS EARTH ATMOSPHERE "AND" OCEANS 
OR REMOTE SENSING APPLICATIONS SOCIETY "AND" ENVIRONMENT 
OR REMOTE SENSING EARTH OCEAN "AND" ATMOSPHERE 
OR REMOTE SENSING FOR LAND SURFACE CHARACTERISATION 
OR REMOTE SENSING IN ECOLOGY "AND" CONSERVATION 
OR REMOTE SENSING INVERSION PROBLEMS "AND" NATURAL HAZARDS 
OR REMOTE SENSING LETTERS OR REMOTE SENSING OF EARTHS SURFACE "AND" ATMOSPHERE 
OR REMOTE SENSING OF ENVIRONMENT OR REMOTE SENSING OF TRACE CONSTITUENTS IN THE LOWER STRATOSPHERE TROPOSPHERE "AND" THE EARTH S SURFACE GLOBAL OBSERVATIONS AIR POLLUTION "AND" THE ATMOSPHERIC CORRECTION OR SCIENCE OF REMOTE SENSING 
OR SOVIET JOURNAL OF REMOTE SENSING
)
```

### General terms

Issue: "GIS" can be used in other contexts, e.g. genome islands, greenland ice sheet, gas-insulated switchgear. However, it is often used in abstracts without being written out in full so can't rely on the full term. Therefore a second phrase is included here (under).

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
    OR "satellite data" OR "satellite derived"
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
            OR "data assimilation" OR "machine learning" OR "kalman filter" OR "EnKF"
            OR "ocean* model*" OR "atmosph* model*"
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

### Satellite missions

Combined those assumed to be more ambiguous with remote sensing terms. Note that the ambiguous terms are not combined with `"remote sensing" OR "earth observation" OR "geographical information system*" OR "GIS" OR "GIScience"` because there is no point - these will be found by phrase 1 anyway.

* Added `TanDEM-X`
* `("Copernicus" NEAR/5 "service*")` should find e.g. copernicus climate change service, copernicus marine service etc.

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
    OR "NeXtSIM" 
    OR ("Copernicus" NEAR/5 "service*")
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
        OR "TOPAZ*"
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
    OR "Land Colo$r Instrument*" OR "Ocean Colo$r Instrument*" OR "Land Surface Temperature Radiomet*" OR "Sea Surface Temperature Radiomet*" 
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
        OR "spectrometry" OR "spectrometer" OR "altimetr*"
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
    OR "ocean state"
    OR "Sea Surface Salinity" OR "SSS" 
    OR "Sea Surface Height" OR "SSH" OR "sea level"
    OR "Sea surface temperature" OR "SST" 
    OR "Ocean Surface Winds" OR "Ocean Surface Currents" OR "Ocean Surface Waves" OR "eddies" OR "eddy"
    OR "Ocean Heat Content" 
    OR "Sea Ice Concentration" OR "Sea Ice Extent" OR "sea ice area" OR "Sea Ice Thickness" OR "Sea Ice Motion" 
    OR "Ice sheet$" OR "Iceberg Detection" OR "Ice Type Classification"
    OR "mass balance"  
    OR "oil spill detection" OR "harmful algal bloom*" OR "harmful algae bloom*"
    OR "operational oceanograph*"
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
        OR "data assimilation" OR "machine learning" OR "kalman filter" OR "EnKF"
        )
)
```

### Agencies - currently not included in string

Difficult to include as seems to find a number of physics papers. Have dropped `satellit*"`, `monitor*`, `optical` and `sensor$` from the second phrase to try and help. I actually suspect that those found by this phrase (and this phrase alone, not the others) are not particularly relevant. Thus this phrase is not currently included in the final search strategy.

```py
TS=
(
    ("European space agency" OR "climate change initiative"
    OR "national aeronautics and space administration"
    OR "Japan Aerospace Exploration Agency" 
    OR "National Oceanic and Atmospheric Administration"
    OR "Indian Space Research Organization"
    OR "China National Space Administration"
    OR "Centre National D’Etudes Spatiales" OR "French Space Agency"
    OR "European Organization for the Exploration of Meteorological Satellites"
    OR "German Aerospace Centre"
    OR "ESA" OR "NASA" OR "JAXA" OR "NOAA" OR "ISRO" OR "CNSA" OR "CNES" OR "EUMETSAT" OR "DLR"
    OR "NORUT"
    OR "Kartverket"
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

## Norwegian terms

* jord observasjon
* jordobservasjon
* fjernmåling
* fjernsansing
* NORUT
* Kartverket
