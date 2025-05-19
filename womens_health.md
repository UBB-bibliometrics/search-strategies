# Women's health search string

Status: In progress unfinished draft.

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
IF CONTAINS(LOWER([scientific_field_npi]), "fødselshjelp og kvinnesykdommer")
THEN 'womenshealth'
ELSE NULL
END
```

### 2. Health issues, diseases, body-terms

These are fetched from conditions listed under two central webpages for women's health (NIH: https://www.nichd.nih.gov/health/topics/womenshealth, Helse Norge: https://www.helsenorge.no/kvinnehelse/) or from publication titles.

English is first, Norwegian is second. Sometimes both languages or variants can be captured by the same term with truncation (e.g. endometrial (EN), endometriosis (EN), endometriose (NO)). 

Body terms are included as these will often capture conditions, e.g. uterine will also capture "uterine fibroids" (and livmor (NO) livmorknuter), ovary will capture "polycystic ovary syndrome", as mentioned on the NIH website.

```
IF CONTAINS(LOWER([result_title]), "women's health") OR CONTAINS(LOWER([result_title]), "womens health") OR CONTAINS(LOWER([result_title]), "kvinnehelse") OR CONTAINS(LOWER([result_title]), "kvinnesykdom")
OR CONTAINS(LOWER([result_title]), "gynecolog") OR CONTAINS(LOWER([result_title]), "gynaecolog") OR CONTAINS(LOWER([result_title]), "obstetric") 

OR CONTAINS(LOWER([result_title]), "amenorrhea") OR CONTAINS(LOWER([result_title]), "amenoré")
OR CONTAINS(LOWER([result_title]), "menarche")
OR CONTAINS(LOWER([result_title]), "menopaus") OR CONTAINS(LOWER([result_title]), "overgangsalder")
OR CONTAINS(LOWER([result_title]), "menstrua") OR REGEXP_MATCH(LOWER([result_title]), "\bmensen")

OR CONTAINS(LOWER([result_title]), "uterine") OR CONTAINS(LOWER([result_title]), "uterus") OR CONTAINS(LOWER([result_title]), "livmor")
OR CONTAINS(LOWER([result_title]), "endometrios") OR REGEXP_MATCH(LOWER([result_title]), "\bendometri") OR CONTAINS(LOWER([result_title]), "endometrios") OR CONTAINS(LOWER([result_title]), "adenomyos")
OR CONTAINS(LOWER([result_title]), "cervix") OR CONTAINS(LOWER([result_title]), "cervical")
OR REGEXP_MATCH(LOWER([result_title]), "\bovary") OR CONTAINS(LOWER([result_title]), "ovarian") OR REGEXP_MATCH(LOWER([result_title]), "\bovari") OR CONTAINS(LOWER([result_title]), "eggstokk")
OR REGEXP_MATCH(([result_title]), "\bPCOS\b")
OR CONTAINS(LOWER([result_title]), "vagina") OR CONTAINS(LOWER([result_title]), "vulva") OR CONTAINS(LOWER([result_title]), "skjede") OR CONTAINS(LOWER([result_title]), "underliv")
OR CONTAINS(LOWER([result_title]), "vulvodyn") OR CONTAINS(LOWER([result_title]), "vaginit") OR CONTAINS(LOWER([result_title]), "vestibulit")
OR CONTAINS(LOWER([result_title]), "thrush") OR CONTAINS(LOWER([result_title]), "soppinfeksjon") OR CONTAINS(LOWER([result_title]), "lichen scler") OR CONTAINS(LOWER([result_title]), "bacterial vagin") OR CONTAINS(LOWER([result_title]), "bakteriell vagino") OR CONTAINS(LOWER([result_title]), "skjedekatar") 
OR CONTAINS(LOWER([result_title]), "female genital") OR CONTAINS(LOWER([result_title]), "kjønnslemlestelse")
OR CONTAINS(LOWER([result_title]), "pelvic floor") OR CONTAINS(LOWER([result_title]), "bekkenbunn")
OR CONTAINS(LOWER([result_title]), "pelvic pain") OR CONTAINS(LOWER([result_title]), "pelvic inflam") OR CONTAINS(LOWER([result_title]), "bekkeninfeksjon")
OR (CONTAINS (LOWER([result_title]), "pelvic") AND CONTAINS (LOWER([result_title]), "prolapse"))

OR CONTAINS(LOWER([result_title]), "pregnan") OR CONTAINS(LOWER([result_title]), "gravid") OR CONTAINS(LOWER([result_title]), "svangerskap")
OR CONTAINS(LOWER([result_title]), "prenatal") OR CONTAINS(LOWER([result_title]), "antenatal") OR CONTAINS(LOWER([result_title]), "postnatal")
OR CONTAINS(LOWER([result_title]), "postpartum") OR CONTAINS(LOWER([result_title]), "barsel")
OR CONTAINS(LOWER([result_title]), "trimester")
OR CONTAINS(LOWER([result_title]), "umbilical") OR CONTAINS(LOWER([result_title]), "placenta") OR CONTAINS(LOWER([result_title]), "morkake")
OR CONTAINS(LOWER([result_title]), "eclampsia") OR CONTAINS(LOWER([result_title]), "eklampsi")
OR CONTAINS(LOWER([result_title]), "birth") OR CONTAINS(LOWER([result_title]), "cesarean") OR CONTAINS(LOWER([result_title]), "fødsel") OR CONTAINS(LOWER([result_title]), "keisersnitt")
OR CONTAINS(LOWER([result_title]), "breastfeed") OR CONTAINS(LOWER([result_title]), "amming") 
OR CONTAINS(LOWER([result_title]), "abortion") OR CONTAINS(LOWER([result_title]), "miscarriage") OR REGEXP_MATCH(LOWER([result_title]), "\babort")
OR CONTAINS(LOWER([result_title]), "contraception") OR CONTAINS(LOWER([result_title]), "birth control") OR CONTAINS(LOWER([result_title]), "prevensjon") 

OR CONTAINS(LOWER([result_title]), "turner's syndrome") OR CONTAINS(LOWER([result_title]), "turner syndrome")
OR CONTAINS(LOWER([result_title]), "fragile x") OR CONTAINS(LOWER([result_title]), "fragilt x")

OR
  ((
  CONTAINS (LOWER([result_title]), "health") OR CONTAINS(LOWER([result_title]), "helse")
  OR CONTAINS(LOWER([result_title]), "mortality") OR CONTAINS(LOWER([result_title]), "død")
  OR CONTAINS(LOWER([result_title]), "clinic") OR CONTAINS(LOWER([result_title]), "klinikk")
  )
  AND
  (
  CONTAINS (LOWER([result_title]), "maternal") OR CONTAINS (LOWER([result_title]), "maternity") OR CONTAINS(LOWER([result_title]), "mother")
  OR REGEXP_MATCH(LOWER([result_title]), "\bmor\b") OR REGEXP_MATCH(LOWER([result_title]), "\bmoren\b") OR CONTAINS(LOWER([result_title]), "mødre")
  ))
THEN 'womenshealth'
ELSE NULL
END

```

### 3. Health issues and diseases with a gender/sex dimension

```
IF
((
CONTAINS(LOWER([scientific_area_npi]), "medisin og helsefag")
OR CONTAINS (LOWER([result_title]), "health") OR CONTAINS(LOWER([result_title]), "helse")
OR CONTAINS(LOWER([result_title]), "mortality") OR CONTAINS(LOWER([result_title]), "død")
OR CONTAINS(LOWER([result_title]), "clinic") OR CONTAINS(LOWER([result_title]), "klinikk")
)
AND
  (
  CONTAINS (LOWER([result_title]), "woman") OR CONTAINS (LOWER([result_title]), "women") OR CONTAINS(LOWER([result_title]), "girl") OR CONTAINS (LOWER([result_title]), "female")
  OR CONTAINS(LOWER([result_title]), "kvinne") OR CONTAINS(LOWER([result_title]), "jente")
  OR CONTAINS(LOWER([result_title]), "gender") OR REGEXP_MATCH(LOWER([result_title]), "\bsex\b")
  ))
THEN 'womenshealth'
ELSE NULL
END
```
