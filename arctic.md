# Arctic research search string

Authors: Caroline S. Armitage and Eli H. Seland, University of Bergen

## Scope
All research publications related to the arctic in the last 10 years. We include "polar" even though this may relate to the south pole too. 

## Search strategy - Tableau

Search is designed for searching in the Cristin database (Norway's national research information system), in Tableau via DUCT (from Sikt). 

The terms are grouped into sections, which are duplicated between result titles, book titles and abstracts:
- geographical places
- geographical oceans/seas
- arctic ice/sea ice
- artic peoples

Norwegian terms are not normally included in the NIB abstract search terms (as this is based on an international database where abstracts are translated to English). Superfluous terms (such as `greenland sea` when `greenland` is included) are removed. 

Terms `ice sheet` and `ice cap` were tested, but mostly added additional works that were not arctic-related. This was also the case for the Norwegian counties `troms` and `finnmark` (particularly much medical research referencing Tromsø or the Tromsø study). `permafrost` was added even though these works can refer to areas outside the arctic - we decided to include it as permafrost mostly occurs in the polar circle. 

Some additional NOT terms are combined with `polar` in the abstract search to avoid other uses of the word, e.g. polar acids, polar lipids. Less necessary with titles search.

```
// Journals
IF REGEXP_MATCH(LOWER([journal]), "\barctic")
OR CONTAINS(LOWER([journal]),	"circumpolar"	)
OR (REGEXP_MATCH(LOWER([journal]), "\bpolar\b") AND NOT CONTAINS(LOWER([journal]),	"offshore and polar"	))
THEN 'arctic'		

// Result titles			
ELSEIF		
REGEXP_MATCH(LOWER([Result Title]), "\barctic") 
OR CONTAINS(LOWER([Result Title]),	"arktisk"	)
OR REGEXP_MATCH(LOWER([Result Title]), "\bpolar\b")
OR REGEXP_MATCH(LOWER([Result Title]), "\bpolare")
OR CONTAINS(LOWER([Result Title]),	"polarforsk"	)
OR CONTAINS(LOWER([Result Title]),	"polarsirke"	)
OR CONTAINS(LOWER([Result Title]),	"polarørken"	)
OR CONTAINS(LOWER([Result Title]),	"polarområde"	)
OR CONTAINS(LOWER([Result Title]),	"polarforsk"	)
OR CONTAINS(LOWER([Result Title]),	"circumpolar"	)
OR CONTAINS(LOWER([Result Title]),	"north pole"	)
OR CONTAINS(LOWER([Result Title]),	"high north"	)
OR CONTAINS(LOWER([Result Title]),	"high-north"	)
OR CONTAINS(LOWER([Result Title]),	"svalbard"	)
OR CONTAINS(LOWER([Result Title]),	"spitsbergen"	)
OR CONTAINS(LOWER([Result Title]),	"longyearbyen"	)	
OR CONTAINS(LOWER([Result Title]),	"bjornoy"	)
OR CONTAINS(LOWER([Result Title]),	"bjørnøy"	)
OR CONTAINS(LOWER([Result Title]),	"jan mayen"	)
OR CONTAINS(LOWER([Result Title]),	"north alaska"	)
OR CONTAINS(LOWER([Result Title]),	"northern quebec"	)
OR CONTAINS(LOWER([Result Title]),	"axel heiberg"	)
OR CONTAINS(LOWER([Result Title]),	"north slope"	)
OR CONTAINS(LOWER([Result Title]),	"prudhoe"	)
OR CONTAINS(LOWER([Result Title]),	"zemlya"	)
OR CONTAINS(LOWER([Result Title]),	"yermak"	)
OR CONTAINS(LOWER([Result Title]),	"franz josef"	)
OR CONTAINS(LOWER([Result Title]),	"northwest territories"	)
OR CONTAINS(LOWER([Result Title]),	"nunavut"	)
OR CONTAINS(LOWER([Result Title]),	"greenland"	)
OR CONTAINS(LOWER([Result Title]),	"grønland"	)	
OR CONTAINS(LOWER([Result Title]),	"nordkalott"	)		
OR CONTAINS(LOWER([Result Title]),	"kola peninsula"	)	
OR CONTAINS(LOWER([Result Title]),	"murmansk"	)	
OR CONTAINS(LOWER([Result Title]),	"kolahalvøy"	)	
OR CONTAINS(LOWER([Result Title]),	"lapland"	)	
OR CONTAINS(LOWER([Result Title]),	"lapin lääni"	)	
OR CONTAINS(LOWER([Result Title]),	"norbotten"	)	
THEN 'arctic'	

ELSEIF
CONTAINS(LOWER([Result Title]),	"barents sea"	)
OR CONTAINS(LOWER([Result Title]),	"norwegian sea"	)
OR CONTAINS(LOWER([Result Title]),	"nordic seas"	)
OR CONTAINS(LOWER([Result Title]),	"ishav"	)
OR CONTAINS(LOWER([Result Title]),	"chukchi sea"	)
OR CONTAINS(LOWER([Result Title]),	"east Siberian sea"	)
OR CONTAINS(LOWER([Result Title]),	"laptev sea"	)
OR CONTAINS(LOWER([Result Title]),	"kara sea"	)
OR CONTAINS(LOWER([Result Title]),	"labroador sea"	)
OR CONTAINS(LOWER([Result Title]),	"Beaufort sea"	)
OR CONTAINS(LOWER([Result Title]),	"Sea of Okhotsk"	)
OR CONTAINS(LOWER([Result Title]),	"weddell sea"	)
OR CONTAINS(LOWER([Result Title]),	"ross sea"	)
OR CONTAINS(LOWER([Result Title]),	"hudson bay"	)
OR CONTAINS(LOWER([Result Title]),	"drake passage"	)
OR CONTAINS(LOWER([Result Title]),	"bering strait"	)
OR CONTAINS(LOWER([Result Title]),	"davis strait"	)
OR CONTAINS(LOWER([Result Title]),	"nares strait"	)
OR CONTAINS(LOWER([Result Title]),	"fram strait"	)
OR CONTAINS(LOWER([Result Title]),	"scotland ridge"	)
THEN 'arctic'		
		
ELSEIF		
CONTAINS(LOWER([Result Title]),	"sea ice"	)
OR CONTAINS(LOWER([Result Title]),	"sea-ice"	)
OR CONTAINS(LOWER([Result Title]),	"ice floe"	)
OR CONTAINS(LOWER([Result Title]),	"pack ice"	)
OR CONTAINS(LOWER([Result Title]),	"polynya"	)
OR CONTAINS(LOWER([Result Title]),	"ice stream"	)
OR CONTAINS(LOWER([Result Title]),	"ice shelves"	)
OR CONTAINS(LOWER([Result Title]),	"ice shelf"	)
OR REGEXP_MATCH(LOWER([Result Title]), "\bnilas\b")
OR CONTAINS(LOWER([Result Title]),	"ice chart"	)
OR CONTAINS(LOWER([Result Title]),	"iceberg"	)
OR CONTAINS(LOWER([Result Title]),	"slush"	)
OR CONTAINS(LOWER([Result Title]),	"pancake ice"	)
OR CONTAINS(LOWER([Result Title]),	"ice ridge"	)
OR CONTAINS(LOWER([Result Title]),	"permafrost"	)
OR CONTAINS(LOWER([Result Title]),	"havis"	)
OR CONTAINS(LOWER([Result Title]),	"sjøis"	)
OR CONTAINS(LOWER([Result Title]),	"isberg")
OR CONTAINS(LOWER([Result Title]),	"isfjell")
THEN 'arctic'		

ELSEIF (		
REGEXP_MATCH(LOWER([Result Title]), "\bsami")
OR REGEXP_MATCH(LOWER([Result Title]), "\bsamer\b")
OR CONTAINS(LOWER([Result Title]),	"sámi"	)
OR CONTAINS(LOWER([Result Title]),	"sápmi"	)
OR CONTAINS(LOWER([Result Title]),	"saami"	)
OR CONTAINS(LOWER([Result Title]),	"sjøsam"	)
OR CONTAINS(LOWER([Result Title]),	"nenets"	)
OR CONTAINS(LOWER([Result Title]),	"khanty"	)
OR CONTAINS(LOWER([Result Title]),	"evenk"	)
OR CONTAINS(LOWER([Result Title]),	"chukchi"	)
OR CONTAINS(LOWER([Result Title]),	"aleut"	)
OR CONTAINS(LOWER([Result Title]),	"yupik "	)
OR REGEXP_MATCH(LOWER([Result Title]), "\binuit")
OR CONTAINS(LOWER([Result Title]),	"kalaallit"	)
OR CONTAINS(LOWER([Result Title]),	"inuvialuit"	)
)			
THEN 'arctic'

// Book titles
ELSEIF		
REGEXP_MATCH(LOWER([Result Title Anthology]), "\barctic") 
OR CONTAINS(LOWER([Result Title Anthology]),	"arktisk"	)
OR REGEXP_MATCH(LOWER([Result Title Anthology]), "\bpolar\b")
OR REGEXP_MATCH(LOWER([Result Title Anthology]), "\bpolare")
OR CONTAINS(LOWER([Result Title Anthology]),	"polarforsk"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"polarsirke"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"polarørken"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"polarområde"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"polarforsk"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"circumpolar"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"north pole"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"high north"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"high-north"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"svalbard"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"spitsbergen"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"longyearbyen"	)	
OR CONTAINS(LOWER([Result Title Anthology]),	"bjornoy"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"bjørnøy"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"jan mayen"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"north alaska"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"northern quebec"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"axel heiberg"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"north slope"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"prudhoe"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"zemlya"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"yermak"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"franz josef"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"northwest territories"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"nunavut"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"greenland"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"grønland"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"nordkalott"	)		
OR CONTAINS(LOWER([Result Title Anthology]),	"kola peninsula"	)	
OR CONTAINS(LOWER([Result Title Anthology]),	"murmansk"	)	
OR CONTAINS(LOWER([Result Title Anthology]),	"kolahalvøy"	)	
OR CONTAINS(LOWER([Result Title Anthology]),	"lapland"	)	
OR CONTAINS(LOWER([Result Title Anthology]),	"lapin lääni"	)	
OR CONTAINS(LOWER([Result Title Anthology]),	"norbotten"	)				
THEN 'arctic'	

ELSEIF
CONTAINS(LOWER([Result Title Anthology]),	"barents sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"norwegian sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"nordic seas"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ishav"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"chukchi sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"east Siberian sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"laptev sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"kara sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"labroador sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"Beaufort sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"Sea of Okhotsk"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"weddell sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ross sea"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"hudson bay"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"drake passage"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"bering strait"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"davis strait"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"nares strait"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"fram strait"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"scotland ridge"	)
THEN 'arctic'		
		
ELSEIF		
CONTAINS(LOWER([Result Title Anthology]),	"sea ice"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"sea-ice"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ice floe"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"pack ice"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"polynya"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ice stream"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ice shelves"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ice shelf"	)
OR REGEXP_MATCH(LOWER([Result Title Anthology]), "\bnilas\b")
OR CONTAINS(LOWER([Result Title Anthology]),	"ice chart"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"iceberg"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"slush"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"pancake ice"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"ice ridge"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"permafrost"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"havis"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"sjøis"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"isberg"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"isfjell")
THEN 'arctic'		

ELSEIF (		
REGEXP_MATCH(LOWER([Result Title Anthology]), "\bsami")
OR REGEXP_MATCH(LOWER([Result Title Anthology]), "\bsamer\b")
OR CONTAINS(LOWER([Result Title Anthology]),	"sámi"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"sápmi"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"saami"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"sjøsam"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"nenets"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"khanty"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"evenk"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"chukchi"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"aleut"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"yupik "	)
OR REGEXP_MATCH(LOWER([Result Title Anthology]), "\binuit")
OR CONTAINS(LOWER([Result Title Anthology]),	"kalaallit"	)
OR CONTAINS(LOWER([Result Title Anthology]),	"inuvialuit"	)
)			
THEN 'arctic'	

// Abstracts		
ELSEIF		
REGEXP_MATCH(LOWER([Nib Abstract]), "\barctic") 
OR (
REGEXP_MATCH(LOWER([Nib Abstract]), "\bpolar\b") 
AND NOT 
    (CONTAINS(LOWER([Nib Abstract]),"polar metabol")
    OR CONTAINS(LOWER([Nib Abstract]),"polar opposit")
    OR CONTAINS(LOWER([Nib Abstract]),"polar lipid")
    OR CONTAINS(LOWER([Nib Abstract]),"polar acid")
    OR CONTAINS(LOWER([Nib Abstract]),"membrane")
    OR CONTAINS(LOWER([Nib Abstract]),"hydroph")
    )
)
OR CONTAINS(LOWER([Nib Abstract]),	"circumpolar"	)
OR CONTAINS(LOWER([Nib Abstract]),	"north pole"	)
OR CONTAINS(LOWER([Nib Abstract]),	"high north"	)
OR CONTAINS(LOWER([Nib Abstract]),	"high-north"	)
OR CONTAINS(LOWER([Nib Abstract]),	"svalbard"	)
OR CONTAINS(LOWER([Nib Abstract]),	"spitsbergen"	)
OR CONTAINS(LOWER([Nib Abstract]),	"longyearbyen"	)	
OR CONTAINS(LOWER([Nib Abstract]),	"bjornoy"	)
OR CONTAINS(LOWER([Nib Abstract]),	"bjørnøy"	)
OR CONTAINS(LOWER([Nib Abstract]),	"jan mayen"	)
OR CONTAINS(LOWER([Nib Abstract]),	"north alaska"	)
OR CONTAINS(LOWER([Nib Abstract]),	"northern quebec"	)
OR CONTAINS(LOWER([Nib Abstract]),	"axel heiberg"	)
OR CONTAINS(LOWER([Nib Abstract]),	"north slope"	)
OR CONTAINS(LOWER([Nib Abstract]),	"prudhoe"	)
OR CONTAINS(LOWER([Nib Abstract]),	"zemlya"	)
OR CONTAINS(LOWER([Nib Abstract]),	"yermak"	)
OR CONTAINS(LOWER([Nib Abstract]),	"franz josef"	)
OR CONTAINS(LOWER([Nib Abstract]),	"northwest territories"	)
OR CONTAINS(LOWER([Nib Abstract]),	"nunavut"	)
OR CONTAINS(LOWER([Nib Abstract]),	"greenland"	)
OR CONTAINS(LOWER([Nib Abstract]),	"grønland"	)			
OR CONTAINS(LOWER([Nib Abstract]),	"nordkalott"	)		
OR CONTAINS(LOWER([Nib Abstract]),	"kola peninsula"	)	
OR CONTAINS(LOWER([Nib Abstract]),	"murmansk"	)	
OR CONTAINS(LOWER([Nib Abstract]),	"lapland"	)	
OR CONTAINS(LOWER([Nib Abstract]),	"norbotten"	)				
THEN 'arctic'	

ELSEIF
CONTAINS(LOWER([Nib Abstract]),	"barents sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"norwegian sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"nordic seas"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ishav"	)
OR CONTAINS(LOWER([Nib Abstract]),	"chukchi sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"east Siberian sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"laptev sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"kara sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"labroador sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"Beaufort sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"Sea of Okhotsk"	)
OR CONTAINS(LOWER([Nib Abstract]),	"weddell sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ross sea"	)
OR CONTAINS(LOWER([Nib Abstract]),	"hudson bay"	)
OR CONTAINS(LOWER([Nib Abstract]),	"drake passage"	)
OR CONTAINS(LOWER([Nib Abstract]),	"bering strait"	)
OR CONTAINS(LOWER([Nib Abstract]),	"davis strait"	)
OR CONTAINS(LOWER([Nib Abstract]),	"nares strait"	)
OR CONTAINS(LOWER([Nib Abstract]),	"fram strait"	)
OR CONTAINS(LOWER([Nib Abstract]),	"scotland ridge"	)
THEN 'arctic'		
		
ELSEIF		
CONTAINS(LOWER([Nib Abstract]),	"sea ice"	)
OR CONTAINS(LOWER([Nib Abstract]),	"sea-ice"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ice floe"	)
OR CONTAINS(LOWER([Nib Abstract]),	"pack ice"	)
OR CONTAINS(LOWER([Nib Abstract]),	"polynya"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ice stream"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ice shelves"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ice shelf"	)
OR REGEXP_MATCH(LOWER([Nib Abstract]), "\bnilas\b")
OR CONTAINS(LOWER([Nib Abstract]),	"ice chart"	)
OR CONTAINS(LOWER([Nib Abstract]),	"iceberg"	)
OR CONTAINS(LOWER([Nib Abstract]),	"slush"	)
OR CONTAINS(LOWER([Nib Abstract]),	"pancake ice"	)
OR CONTAINS(LOWER([Nib Abstract]),	"ice ridge"	)
OR CONTAINS(LOWER([Nib Abstract]),	"permafrost"	)
THEN 'arctic'		

ELSEIF (		
REGEXP_MATCH(LOWER([Nib Abstract]), "\bsami")
OR REGEXP_MATCH(LOWER([Nib Abstract]), "\bsamer\b")
OR CONTAINS(LOWER([Nib Abstract]),	"sámi"	)
OR CONTAINS(LOWER([Nib Abstract]),	"sápmi"	)
OR CONTAINS(LOWER([Nib Abstract]),	"saami"	)
OR CONTAINS(LOWER([Nib Abstract]),	"sjøsam"	)
OR CONTAINS(LOWER([Nib Abstract]),	"nenets"	)
OR CONTAINS(LOWER([Nib Abstract]),	"khanty"	)
OR CONTAINS(LOWER([Nib Abstract]),	"evenk"	)
OR CONTAINS(LOWER([Nib Abstract]),	"chukchi"	)
OR CONTAINS(LOWER([Nib Abstract]),	"aleut"	)
OR CONTAINS(LOWER([Nib Abstract]),	"yupik "	)
OR REGEXP_MATCH(LOWER([Nib Abstract]), "\binuit")
OR CONTAINS(LOWER([Nib Abstract]),	"kalaallit"	)
OR CONTAINS(LOWER([Nib Abstract]),	"inuvialuit"	)
)			
THEN 'arctic'
		
ELSE "non"
END
```
