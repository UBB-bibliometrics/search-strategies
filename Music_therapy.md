# Music therapy search string

## Scope
All publications originating from the multi institutional research cluster "Polyfon" in 2023 - for annual report

## Search strategy 

Search in Cristin for 2023 publications, using keywords in Norwegian and English, in combination with institution and journal names 

```

// Journals
IF CONTAINS(LOWER([journal]), "music therapy")
THEN 'music therapy'            

// Result titles
ELSEIF
CONTAINS(LOWER([Result Title]), "music therap")
OR CONTAINS(LOWER([Result Title]), "musikkterap")
OR CONTAINS ((LOWER([Result Title]), "music") AND (LOWER([Result Title]), "health"))
OR CONTAINS ((LOWER([Result Title]), "musik") AND (LOWER([Result Title]), "helse")) 


-	Musikkterapi
-	Music therapy
-	Musikk
-	Musikk og helse
-	Music
-	Music and health
-	Spilling 
-	Spille 
-	Playing 
-	Play 
-	Improvisasjon 
-	Improvisere
-	Improvisation 
-	Improvise 
-	Komposisjon
-	Komponere 
-	Composition
-	Compose
-	Songwriting
-	Sangskriving
-	Lytting
-	Lytte
-	Listening
-	Listen


// Institutions
(LOWER([unit_level_3]), "Griegakademiet")
(LOWER([unit_level_3]), "NORCE Helse og samfunn - GAMUT")
// NMH
(LOWER([institution]), "Norges musikkhøgskole")
(LOWER([unit_level_3]), "Fagseksjon for musikkpedagogikk og musikkterapi")
(LOWER([unit_level_3]), "NORCE Helse og samfunn - GAMUT")
// HVL
(LOWER([institution]), "høgskulen på Vestlandet")
(LOWER([unit_level_2]), "Fakultet for helse- og sosialvitskap")
(LOWER([unit_level_2]), "Fakultet for lærarutdanning, kultur og idrett")
(LOWER([institution]), "helse Bergen HF")
(LOWER([institution]), "helse fonna HF")
(LOWER([institution]), "helse førde HF")
(LOWER([unit_level_2]), "NKS Olaviken alderspsykiatriske sykehus")
(LOWER([unit_level_2]), "Betanien sykehus")

//- Universitetet i Bergen, Griegakademiet
-	NORCE, Helse og Samfunn, GAMUT
-	Norges Musikkhøgskole, Fagseksjon for musikkpedagogikk og musikkterapi (forskingssenteret CREMAH om mulig)
-	Høgskulen på Vestlandet
-	Helse Bergen
-	Helse Fonna
-	Helse Førde
-	NKS Olaviken alderspsykiatriske sjukehus (i Cristin: velg enhet «Private ideelle i Helse Vest» for å få opp Olaviken som alternativ)
-	Betanien sjukehus (i Cristin: velg enhet «Private ideelle i Helse Vest» for å få opp Betanien som alternativ)


```
