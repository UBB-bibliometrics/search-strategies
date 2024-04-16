# Music therapy search string

## Scope
Publications about music therapy in Cristin 

## Search strategy 

Search in Cristin for publications, using keywords in Norwegian and English, in combination with journal, book and anthology names 

```

// STRING FOR TESTING: Under development

IF CONTAINS(LOWER([journal]), "music therapy") 
OR CONTAINS(LOWER([journal]), "musikkterapi")
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
OR CONTAINS(LOWER([result_title]), "listen")
OR CONTAINS(LOWER([result_title]), "rhythmic")
)
AND
(
CONTAINS (LOWER([result_title]), "therap")
OR CONTAINS(LOWER([result_title]), "health")
OR CONTAINS(LOWER([result_title]), "rehabilit")
OR CONTAINS(LOWER([result_title]), "clinic")
OR CONTAINS(LOWER([result_title]), "intervention")
OR CONTAINS(LOWER([result_title]), "depress")
OR CONTAINS(LOWER([result_title]), "trauma")
OR CONTAINS(LOWER([result_title]), "dementia")
OR CONTAINS(LOWER([result_title]), "autis")
OR CONTAINS(([result_title]), "PTSD")
OR CONTAINS(([result_title]), "ADHD")
OR CONTAINS(LOWER([result_title]), "prison")
OR CONTAINS(LOWER([result_title]), "hospital")
OR CONTAINS(LOWER([result_title]), "care home")
OR CONTAINS(LOWER([result_title]), "care unit")
))

OR
((
CONTAINS (LOWER([result_title]), "musik")
OR CONTAINS(LOWER([result_title]), "improvis")
OR CONTAINS(LOWER([result_title]), "komponer")
OR CONTAINS(LOWER([result_title]), "komposisjon")
OR CONTAINS(LOWER([result_title]), "sang")
OR CONTAINS(LOWER([result_title]), "syng")
OR REGEXP_MATCH(LOWER([result_title]), "\bkor\b")
OR CONTAINS(LOWER([result_title]), "lytt")
OR CONTAINS(LOWER([result_title]), "rytmisk")
)
AND
(
CONTAINS (LOWER([result_title]), "terap")
OR CONTAINS(LOWER([result_title]), "helse")
OR CONTAINS(LOWER([result_title]), "rehabilit")
OR CONTAINS(LOWER([result_title]), "klinisk")
OR CONTAINS(LOWER([result_title]), "intervensjon")
OR CONTAINS(LOWER([result_title]), "depresjon")
OR CONTAINS(LOWER([result_title]), "deprimert")
OR CONTAINS(LOWER([result_title]), "traum")
OR CONTAINS(LOWER([result_title]), "demen")
OR CONTAINS(LOWER([result_title]), "autis")
OR CONTAINS(([result_title]), "PTSD")
OR CONTAINS(([result_title]), "ADHD")
OR CONTAINS(LOWER([result_title]), "fengsel")
OR CONTAINS(LOWER([result_title]), "omsorg")
OR CONTAINS(LOWER([result_title]), "sykehus")
OR CONTAINS(LOWER([result_title]), "sjukehus")
OR CONTAINS(LOWER([result_title]), "sykehjem")
OR CONTAINS(LOWER([result_title]), "sjukeheim")
OR CONTAINS(LOWER([result_title]), "aldershjem")
OR CONTAINS(LOWER([result_title]), "aldersheim")
))

OR
CONTAINS(LOWER([result_title_anthology]), "music therap")
OR CONTAINS(LOWER([result_title_anthology]), "musikkterap")
OR
((
CONTAINS (LOWER([result_title_anthology]), "music")
OR CONTAINS(LOWER([result_title_anthology]), "improvis")
OR CONTAINS(LOWER([result_title_anthology]), "songwrit")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bsing\b")
OR CONTAINS(LOWER([result_title_anthology]), "singer")
OR CONTAINS(LOWER([result_title_anthology]), "singing")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bchoir")
OR CONTAINS(LOWER([result_title_anthology]), "listen")
OR CONTAINS(LOWER([result_title_anthology]), "rhythmic")
)
AND
(
CONTAINS (LOWER([result_title_anthology]), "therap")
OR CONTAINS(LOWER([result_title_anthology]), "health")
OR CONTAINS(LOWER([result_title_anthology]), "rehabilit")
OR CONTAINS(LOWER([result_title_anthology]), "clinic")
OR CONTAINS(LOWER([result_title_anthology]), "intervention")
OR CONTAINS(LOWER([result_title_anthology]), "depress")
OR CONTAINS(LOWER([result_title_anthology]), "trauma")
OR CONTAINS(LOWER([result_title_anthology]), "dementia")
OR CONTAINS(LOWER([result_title_anthology]), "autis")
OR CONTAINS(([result_title_anthology]), "PTSD")
OR CONTAINS(([result_title_anthology]), "ADHD")
OR CONTAINS(LOWER([result_title_anthology]), "prison")
OR CONTAINS(LOWER([result_title_anthology]), "hospital")
OR CONTAINS(LOWER([result_title_anthology]), "care home")
OR CONTAINS(LOWER([result_title_anthology]), "care unit")
))

OR
((
CONTAINS (LOWER([result_title_anthology]), "musik")
OR CONTAINS(LOWER([result_title_anthology]), "improvis")
OR CONTAINS(LOWER([result_title_anthology]), "komponer")
OR CONTAINS(LOWER([result_title_anthology]), "komposisjon")
OR CONTAINS(LOWER([result_title_anthology]), "sang")
OR CONTAINS(LOWER([result_title_anthology]), "syng")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bkor\b")
OR CONTAINS(LOWER([result_title_anthology]), "lytt")
OR CONTAINS(LOWER([result_title_anthology]), "rytmisk")
)
AND
(
CONTAINS (LOWER([result_title_anthology]), "terap")
OR CONTAINS(LOWER([result_title_anthology]), "helse")
OR CONTAINS(LOWER([result_title_anthology]), "rehabilit")
OR CONTAINS(LOWER([result_title_anthology]), "klinisk")
OR CONTAINS(LOWER([result_title_anthology]), "intervensjon")
OR CONTAINS(LOWER([result_title_anthology]), "depresjon")
OR CONTAINS(LOWER([result_title_anthology]), "deprimert")
OR CONTAINS(LOWER([result_title_anthology]), "traum")
OR CONTAINS(LOWER([result_title_anthology]), "demen")
OR CONTAINS(LOWER([result_title_anthology]), "autis")
OR CONTAINS(([result_title_anthology]), "PTSD")
OR CONTAINS(([result_title_anthology]), "ADHD")
OR CONTAINS(LOWER([result_title_anthology]), "fengsel")
OR CONTAINS(LOWER([result_title_anthology]), "omsorg")
OR CONTAINS(LOWER([result_title_anthology]), "sykehus")
OR CONTAINS(LOWER([result_title_anthology]), "sjukehus")
OR CONTAINS(LOWER([result_title_anthology]), "sykehjem")
OR CONTAINS(LOWER([result_title_anthology]), "sjukeheim")
OR CONTAINS(LOWER([result_title_anthology]), "aldershjem")
OR CONTAINS(LOWER([result_title_anthology]), "aldersheim")
))

THEN 'music therapy'
ELSE NULL
END




```
//Notes:
// 
- Universitetet i Bergen, Griegakademiet 184-18-30
-	NORCE, Helse og Samfunn, GAMUT 2057-2-2-
-	Norges Musikkhøgskole, Fagseksjon for musikkpedagogikk og musikkterapi (forskingssenteret CREMAH om mulig) 178-3-7
-	Høgskulen på Vestlandet 203-10 og 11
-	Helse Bergen 1936
-	Helse Fonna 1932
-	Helse Førde 1935
-	NKS Olaviken alderspsykiatriske sykehus (i Cristin: velg enhet «Private ideelle i Helse Vest» for å få opp Olaviken som alternativ)1937-1
-	Betanien sykehus (i Cristin: velg enhet «Private ideelle i Helse Vest» for å få opp Betanien som alternativ)1937-3

