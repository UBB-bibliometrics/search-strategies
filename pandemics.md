# Pandemic research

Authors: Caroline S. Armitage, University of Bergen

Bestilling: Pandemic Centre at UiB

**WORK IN PROGRESS 12/09/24**

## Scope

Everything that mentions the covid-19 or the covid-19 pandemic in any capacity/context or discipline, from Norwegian institutions. Should find results both in English and Norwegian, and of diverse publication types (articles, books, chapters, reports, dissertations; but not media outputs or datasets).

Timespan: Publication date = 2020-01-01 to 2024 as much as possible

## Other strings used/copied

The following strings were used for inspiration, to find terminology, and in some cases lines are copied from:

- PubMed covid-19 article filters: https://pubmed.ncbi.nlm.nih.gov/help/#covid19-article-filters
- Canada's Drug Agency covid-19 search strings: https://www.cda-amc.ca/literature-searching-tools/covid-19-search-strings
- Carrie Price MLS: https://carrieprice78.github.io/guides/search-filters/coronavirus/

## Search strings

Two search strings are included: one for Web of Science (Clarivate) (English only; Topic (title, abstract, keywords, keywordsplus) and one for running against Norway's national CRIS system (Cristin) via Tableau DUCT (from Sikt) (English and Norwegian; title search only).

As we are restricting the search to 2020 onwards, we can potentially simplify the search for coronavirus terms (i.e. go broader, not specify which coronavirus). 

### Search string, Web of Science

#1

```py
TS=(
"coronavirus*" OR "corona virus*" OR "covid"
OR "COVID19*" OR "COVID2019" OR "COVID-19*" OR "COVID-2019*" 
OR "SARS-CoV-2019" OR "SARS-CoV-19"
OR "SARS-CoV-2" OR "SARS-COV2" OR "SARSCOV-2" OR "SARSCOV2" OR "SARSCoV"
OR "NCOV" OR "2019-nCoV" OR "2019nCoV" OR "SARS-nCoV" OR "SARSnCoV"
OR "pandemic*"
)
```

#2

- Originally this search contained a line for PPE - but many other fields use these terms (e.g. firefighters, construction workers), and the abbreviation is used for many other things. In practice, this part of the search only adds two additional results for Norway in the target years, and these are not specifically about the pandemic, therefore it is dropped. Original search tested: `(("personal protective equipment") NOT ("construction" OR "firefight*" OR "kiln" OR "cement" OR "police" OR "recycl*" OR "radiation" OR "ship*" OR "oil" OR "H2S" OR "mining" OR "miner*" OR "mercury" OR "heavy metal*" OR "soot" OR "agricult*" OR "farm*" OR "pesticide*" OR "cold"))`
- Face mask results are not always about the pandemic but do mostly seem to be about medical face masks. I have tried to exclude results about neonatal ventilation/resuscitation, which also use face masks.

```py
TS=(
"facemask*" OR "face mask*" OR "surgical mask*" OR "face shield*" OR "FFP1" OR "FFP2"
OR (("N99" OR "N95" OR "N 99" OR "N 95" OR "FFP" OR "P100") NEAR/3 "respirator*")
OR 	(("respiratory" OR "facial" OR "N99" OR "N95" OR "N 99" OR "N 95")
	NEAR/3 ("mask" OR "masks")
	)
)
NOT TS=("neonatal" OR "newborn" OR "resuscitation")
```

#3

Here I tried with "social distanc*" but "social distance" seems to be mostly about non-pandemic topics, which "distancing" is much more focused. 

```py
TS=("lockdown*" OR "social distancing" OR "physical distancing")
```

#4
```py
#1 OR #2 OR #3
```

### Search string, Cristin

Title search only.

- "Corona" is limited to avoid "coronary". While "PPE"/"personal protective equipment" are in theory good terms, they do not add any additional relevant results when searching Cristin and are therefore dropped.
- Use of mask types only adds noise, so is dropped

```py
IF 
CONTAINS(LOWER([result_title]),	"pandemi"	)
OR CONTAINS(LOWER([result_title]),	"covid"	)
OR CONTAINS(LOWER([result_title]),	"coronavirus"	)
OR REGEXP_MATCH(LOWER([result_title]), "\bcorona\b")
OR CONTAINS(LOWER([result_title]),	"korona"	)
OR REGEXP_MATCH(([result_title]), "\bSARS")
OR REGEXP_MATCH(LOWER([result_title]), "\bncov")
OR REGEXP_MATCH(LOWER([result_title]), "\bsars-cov")
OR REGEXP_MATCH(LOWER([result_title]), "\bsarscov")
OR REGEXP_MATCH(([result_title]), "\bCoV\b")
OR REGEXP_MATCH(([result_title]), "\bCoV2\b")
OR REGEXP_MATCH(([result_title]), "\bCOV\b")
OR REGEXP_MATCH(([result_title]), "\bCOV2\b")

OR CONTAINS(LOWER([result_title]),	"face mask"	)
OR CONTAINS(LOWER([result_title]),	"facemask"	)
OR CONTAINS(LOWER([result_title]),	"ansiktsmask"	)
//OR CONTAINS(LOWER([result_title]),	"personal protective equipment"	)
//OR REGEXP_MATCH(([result_title]), "\bPPE\b")

OR CONTAINS(LOWER([result_title]),	"quarantine"	)
OR CONTAINS(LOWER([result_title]),	"karantene"	)
OR CONTAINS(LOWER([result_title]),	"lock-down"	)
OR CONTAINS(LOWER([result_title]),	"lockdown"	)
OR CONTAINS(LOWER([result_title]),	"nedstenging"	)
OR CONTAINS(LOWER([result_title]),	"skolestenging"	)
OR CONTAINS(LOWER([result_title]),	"en-metersregel"	)
OR CONTAINS(LOWER([result_title]),	"en metersregel"	)
THEN "pandemic"

ELSEIF 
CONTAINS(LOWER([result_title_anthology]),	"pandemi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"covid"	)
OR CONTAINS(LOWER([result_title_anthology]),	"coronavirus"	)
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bcorona\b")
OR CONTAINS(LOWER([result_title_anthology]),	"korona"	)
OR REGEXP_MATCH(([result_title_anthology]), "\bSARS")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bsars-cov")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bsarscov")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bncov")
OR REGEXP_MATCH(([result_title_anthology]), "\bCoV\b")
OR REGEXP_MATCH(([result_title_anthology]), "\bCoV2\b")
OR REGEXP_MATCH(([result_title_anthology]), "\bCOV\b")
OR REGEXP_MATCH(([result_title_anthology]), "\bCOV2\b")

OR CONTAINS(LOWER([result_title_anthology]),	"face mask"	)
OR CONTAINS(LOWER([result_title_anthology]),	"facemask"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ansiktsmask"	)
//OR CONTAINS(LOWER([result_title_anthology]),	"personal protective equipment"	)
//OR REGEXP_MATCH(([result_title_anthology]), "\bPPE\b")

OR CONTAINS(LOWER([result_title_anthology]),	"quarantine"	)
OR CONTAINS(LOWER([result_title_anthology]),	"karantene"	)
OR CONTAINS(LOWER([result_title_anthology]),	"lock-down"	)
OR CONTAINS(LOWER([result_title_anthology]),	"lockdown"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nedstenging"	)
OR CONTAINS(LOWER([result_title_anthology]),	"skolestenging"	)
OR CONTAINS(LOWER([result_title_anthology]),	"en-metersregel"	)
OR CONTAINS(LOWER([result_title_anthology]),	"en metersregel"	)
THEN "pandemic"

END
```
