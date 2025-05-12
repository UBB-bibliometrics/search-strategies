# Women's health search string

Author: Caroline Armitage, University of Bergen

Task: Mapping of publications from DRIV, the Center for Research on Women's Health at UiB (https://www.uib.no/en/driv), May 2025. Recieved from an advisor at DRIV.

## Scope

Publications about women's health in Norwegian and English. Scientific publications. 

Women's health is defined by the centre to include health issues specific to women and girls, as well as research on health issues that affect male and female peoeple differently, or otherwise disproportionately affect female people. 

## Search strategy 

Search in Cristin for publications, using keywords in Norwegian and English, in combination with journal, book and anthology names. 
The search is designed for searching in the Cristin database (Norway's national research information system), in Tableau via DUCT (from Sikt). 

The search strategy also includes searches for publications from specific people known to work in Women's health at the centre, but this part is not included here. 

Finding publications within the scope is challenging because we do not have an exhaustive definitive list of the health issues that should be included under "women's health". 
For example, research about how a disease affects women vs. men may be relevant even though the disease is not a traditional "women's health" disease. 
We therefore take multiple approaches for the search strategy:
1. All publications published in journals under the Norwegian Publishing Indicator category for Gynaecology and Obstetrics (https://npi.hkdir.no/fagfeltoversikt/fagfelt?id=1069)
2. Search terms for female-specific health issues, diseases, or body terms
3. Search terms for general diseases/health that are combined with a gender/sex/female dimension

### 1. NPI Gynaecology and Obstetrics

```
IF CONTAINS(LOWER([scientfic_field_npi]), "fødselshjelp og kvinnesykdommer")
THEN 'womenshealth'
ELSE NULL
END
```

### 2. Health issues, diseases, body-terms

These are fetched from conditions listed under two central webpages for women's health (NIH: https://www.nichd.nih.gov/health/topics/womenshealth, Helse Norge: https://www.helsenorge.no/kvinnehelse/) or from publication titles.

```
//**PLACEHOLDER**

IF CONTAINS(LOWER([scientfic_field_npi]), "fødselshjelp og kvinnesykdommer") 
ELSE NULL
END
OR
CONTAINS(LOWER([result_title]), "music therap")
OR CONTAINS(LOWER([result_title]), "musikkterap")
OR
((
CONTAINS (LOWER([result_title]), "music")
OR CONTAINS(LOWER([result_title]), "improvis")
OR CONTAINS(LOWER([result_title]), "songwrit")
OR REGEXP_MATCH(LOWER([result_title]), "\bsing\b")
OR CONTAINS(LOWER([result_title]), "singer")
OR CONTAINS(LOWER([result_title]), "singing")
OR REGEXP_MATCH(LOWER([result_title]), "\bchoir")
)
AND
(
CONTAINS (LOWER([result_title]), "therap")
OR CONTAINS(LOWER([result_title]), "health")
))

THEN 'womenshealth'
ELSE NULL
END

```

### 3. Health issues and diseases with a gender/sex dimension


