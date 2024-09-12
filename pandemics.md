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

## Search strings

Two search strings are included: one for Web of Science (Clarivate) (English only; Topic (title, abstract, keywords, keywordsplus) and one for running against Norway's national CRIS system (Cristin) via Tableau DUCT (from Sikt) (English and Norwegian; title search only).

As we are restricting the search to 2020 onwards, we can potentially simplify the search for coronavirus terms (i.e. go broader, not specify which coronavirus). 

### Search string, Web of Science

#1

```py
TS=(
"coronavirus" OR "covid"
OR "COVID19*" OR "COVID2019" OR "COVID-19*" OR "COVID-2019*" OR "2019-nCoV" OR "SARS-CoV-2019" OR "SARS-CoV-2" OR "SARS-COV2" OR "SARSCOV-2" OR "SARSCOV2" OR "SARS-CoV-19" OR "NCOV"
OR "pandemic*"
)
```

#2

The PPE part of this search is difficult - many other fields use these terms (e.g. firefighters, construction workers), and the abbreviation is used for many other things. Face mask results are not always about the pandemic but do mostly seem to be about medical face masks. 

```py
TS=(
"facemask*" OR "face mask*" OR "face shield*" OR "FFP1" OR "FFP2"
OR 	(("surgical" OR "respiratory" OR "protect*" OR "facial" OR "face" OR "N99" OR "N95" OR "N 99" OR "N 95")
	NEAR/3 "mask*"
	)
OR (("N99" OR "N95" OR "N 99" OR "N 95" OR "FFP" OR "P100") NEAR/3 "respirator*")
OR 	(("personal protective equipment")
	NOT ("construction" OR "firefight*" OR "kiln" OR "cement" OR "police" OR "recycl*" OR "radiation"
	OR "ship*" OR "oil" OR "H2S" OR "mining" OR "miner*" OR "mercury" OR "heavy metal*"
	OR "soot" OR "agricult*" OR "farm*" OR "pesticide*" OR "cold")
	)
)
```

#3

Here I tried with "social distanc*" but "social distance" seems to be mostly about non-pandemic topics, which "distancing" is much more focused. 

```py
TS=(
"lockdown" OR "social distancing" OR "physical distancing"
)
```

#4
```py
#1 OR #2 OR #3
```

### Search string, Cristin

Title search only.

```py
IF 
CONTAINS(LOWER([result_title]),	"pandemi"	)
OR CONTAINS(LOWER([result_title]),	"covid"	)
OR CONTAINS(LOWER([result_title]),	"corona"	)
OR CONTAINS(LOWER([result_title]),	"korona"	)
OR REGEXP_MATCH(([result_title]), "\bSARS")
OR REGEXP_MATCH(LOWER([result_title]), "\bncov")

OR CONTAINS(LOWER([result_title]),	"face mask"	)
OR CONTAINS(LOWER([result_title]),	"facemask"	)
OR CONTAINS(LOWER([result_title]),	"ansiktsmask"	)
OR CONTAINS(LOWER([result_title]),	"personal protective equipment"	)
OR REGEXP_MATCH(([result_title]), "\bPPE\b")

OR CONTAINS(LOWER([result_title]),	"quarantine"	)
OR CONTAINS(LOWER([result_title]),	"karantene"	)
OR CONTAINS(LOWER([result_title]),	"lock-down"	)
OR CONTAINS(LOWER([result_title]),	"lockdown"	)
OR CONTAINS(LOWER([result_title]),	"nedstenging"	)
OR CONTAINS(LOWER([result_title]),	"skolestenging"	)
OR CONTAINS(LOWER([result_title]),	"en-metersregel"	)
OR CONTAINS(LOWER([result_title]),	"en metersregel"	)

THEN "pandemic"
END
```
