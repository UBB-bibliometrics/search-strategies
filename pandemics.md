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

Two search strings are included: one for Web of Science (Clarivate) (English only) and one for running against Norway's national CRIS system (Cristin) via Tableau DUCT (from Sikt) (English and Norwegian).

As we are restricting the search to 2020 onwards, we can potentially simplify the search for coronavirus terms (i.e. go broader, not specify which coronavirus). 

### Search string, Web of Science

```py
TS=(
"coronavirus" OR "covid"
OR "COVID19*" OR "COVID2019" OR "COVID-19*" OR "COVID-2019*" OR "2019-nCoV" OR "SARS-CoV-2019" OR "SARS-CoV-2" OR "SARS-CoV-19" OR "NCOV"
OR "pandemic*"
)
```

```py
TS=(
"personal protective equipment" OR "PPE" OR "PPEs"
OR "facemask*" OR "face mask*" OR "face shield*" OR "FFP1" OR "FFP2"
OR (("surgical" OR "respiratory" OR "protect*" OR "facial" OR "face" OR "N99" OR "N95" OR "N 99" OR "N 95") NEAR/3 "mask*")
)
```


### Search string, Cristin

```py

```
