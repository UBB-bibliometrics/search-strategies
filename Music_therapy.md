# Music therapy search string

## Scope
All publications originating from the multi institutional research cluster "Polyfon" in 2023 - for annual report

## Search strategy 

Search in Cristin for 2023 publications, using keywords in Norwegian and English, in combination with institution and journal names 

```

// STRING FOR TESTING: Under development
//Journals

IF CONTAINS(LOWER([journal]), "music therapy")           

OR
CONTAINS(LOWER([result_title]), "music therap")
OR CONTAINS(LOWER([result_title]), "musikkterap")
OR
((
CONTAINS (LOWER([result_title]), "music")
OR CONTAINS (LOWER([result_title]), "play")
OR CONTAINS(LOWER([result_title]), "improvis")
OR CONTAINS(LOWER([result_title]), "songwrit")
OR CONTAINS(LOWER([result_title]), "sing")
OR CONTAINS(LOWER([result_title]), "listen")
)
AND
(
CONTAINS (LOWER([result_title]), "therap")
OR CONTAINS(LOWER([result_title]), "health")
OR CONTAINS(LOWER([result_title]), "clinic")
OR CONTAINS(LOWER([result_title]), "intervention")
OR CONTAINS(LOWER([result_title]), "depress")
OR CONTAINS(LOWER([result_title]), "trauma")
OR CONTAINS(LOWER([result_title]), "dementia")
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
OR CONTAINS (LOWER([result_title]), "spill")
OR CONTAINS(LOWER([result_title]), "improvis")
OR CONTAINS(LOWER([result_title]), "komponer")
OR CONTAINS(LOWER([result_title]), "komposisjon")
OR CONTAINS(LOWER([result_title]), "sang")
OR CONTAINS(LOWER([result_title]), "syng")
OR CONTAINS(LOWER([result_title]), "lytt")
)
AND
(
CONTAINS (LOWER([result_title]), "terap")
OR CONTAINS(LOWER([result_title]), "helse")
OR CONTAINS(LOWER([result_title]), "klinisk")
OR CONTAINS(LOWER([result_title]), "intervensjon")
OR CONTAINS(LOWER([result_title]), "depresjon")
OR CONTAINS(LOWER([result_title]), "deprimert")
OR CONTAINS(LOWER([result_title]), "traum")
OR CONTAINS(LOWER([result_title]), "demen")
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

THEN 'music therapy'
ELSE NULL
END

```
//Notes:
// Institutions
CONTAINS(LOWER([unit_level_3]), "Griegakademiet")
OR CONTAINS(LOWER([unit_level_3]), "NORCE Helse og samfunn - GAMUT")
// NMH
OR CONTAINS(LOWER([institution]), "Norges musikkhøgskole")
OR CONTAINS(LOWER([unit_level_3]), "Fagseksjon for musikkpedagogikk og musikkterapi")
OR CONTAINS(LOWER([unit_level_3]), "NORCE Helse og samfunn - GAMUT")
// HVL
OR
(
(CONTAINS(LOWER([institution]), "høgskulen på Vestlandet"))
AND
(CONTAINS(LOWER([unit_level_2]), "Fakultet for helse- og sosialvitskap")
OR CONTAINS(LOWER([unit_level_2]), "Fakultet for lærarutdanning, kultur og idrett"))
)
OR CONTAINS(LOWER([institution]), "helse Bergen HF")
OR CONTAINS(LOWER([institution]), "helse fonna HF")
OR CONTAINS(LOWER([institution]), "helse førde HF")
OR CONTAINS(LOWER([unit_level_2]), "NKS Olaviken alderspsykiatriske sykehus")
OR CONTAINS(LOWER([unit_level_2]), "Betanien sykehus"))


//- Universitetet i Bergen, Griegakademiet 184-18-30
-	NORCE, Helse og Samfunn, GAMUT 2057-2-2-
-	Norges Musikkhøgskole, Fagseksjon for musikkpedagogikk og musikkterapi (forskingssenteret CREMAH om mulig) 178-3-7
-	Høgskulen på Vestlandet 203-10 og 11
-	Helse Bergen 1936
-	Helse Fonna 1932
-	Helse Førde 1935
-	NKS Olaviken alderspsykiatriske sykehus (i Cristin: velg enhet «Private ideelle i Helse Vest» for å få opp Olaviken som alternativ)1937-1
-	Betanien sykehus (i Cristin: velg enhet «Private ideelle i Helse Vest» for å få opp Betanien som alternativ)1937-3

