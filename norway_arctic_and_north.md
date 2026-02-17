# Northern Norway and Arctic Norway research search string

Authors: Caroline S. Armitage, University of Bergen Library

Two search strings: One for Tableau, one for Web of Science.

## Scope
All research publications related to Northern Norway and the Arctic areas closest to Norway. 

Northern Norway is defined as the 3 northern fylker (Finnmark, Troms, Nordland).

> "I stortingsmelding 9 (2020-2021) Mennesker, muligheter og norske interesser i nord definerte Utenriksdepartementet nordområdene som «land- og havområdene fra Sør-Helgeland i sør til Grønlandshavet i vest og Petsjorahavet (det sørøstlige hjørnet av Barentshavet) i øst. Begrepet er særlig forbundet med ivaretagelse av norske interesser gjennom ulike satsinger og grenseoverskridende samarbeid på Nordkalotten og i Barentsregionen." https://snl.no/stortingsmelding

The seas and oceans included may expand on this definition slightly to improve recall. The search string may find research to do with Antarctica/south polar areas, which will need to be excluded manually. 

## Search strategy - Tableau

Search is designed for searching in the Cristin database (Norway's national research information system), in Tableau via DUCT (from Sikt). 

The terms are grouped into sections, which are duplicated between result titles and book titles:
- geographical/oceanic places
- arctic ice/sea ice
- artic/northern peoples
- northern Norway places
- arctic shipping routes


```
// Journals
IF REGEXP_MATCH(LOWER([journal]), "\barctic")
OR CONTAINS(LOWER([journal]),	"circumpolar"	)
OR REGEXP_MATCH(LOWER([journal]), "\bpolar\b") 
THEN 'nordnorge and arctic'		

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
OR CONTAINS(LOWER([Result Title]),	"edgeøya"	)
OR CONTAINS(LOWER([Result Title]),	"edge island"	)
OR CONTAINS(LOWER([Result Title]),	"barentsøya"	)
OR CONTAINS(LOWER([Result Title]),	"barents island"	)
OR CONTAINS(LOWER([Result Title]),	"longyearbyen"	)	
OR CONTAINS(LOWER([Result Title]),	"bjornoy"	)
OR CONTAINS(LOWER([Result Title]),	"bjørnøy"	)
OR CONTAINS(LOWER([Result Title]),	"bear island"	)
OR CONTAINS(LOWER([Result Title]),	"jan mayen"	)
OR CONTAINS(LOWER([Result Title]),	"zemlya"	)
OR CONTAINS(LOWER([Result Title]),	"novaja semlja"	)
OR CONTAINS(LOWER([Result Title]),	"franz josef"	)
OR CONTAINS(LOWER([Result Title]),	"frans josef"	)
OR CONTAINS(LOWER([Result Title]),	"zemlja frantsa"	)
OR CONTAINS(LOWER([Result Title]),	"nordkalott"	)
OR CONTAINS(LOWER([Result Title]),	"north calotte"	)
OR CONTAINS(LOWER([Result Title]),	"greenland"	)
OR CONTAINS(LOWER([Result Title]),	"grønland"	)	
	
OR CONTAINS(LOWER([Result Title]),	"kola peninsula"	)	
OR CONTAINS(LOWER([Result Title]),	"murmansk"	)	
OR CONTAINS(LOWER([Result Title]),	"kolahalvøy"	)	
OR CONTAINS(LOWER([Result Title]),	"lapland"	)	
OR CONTAINS(LOWER([Result Title]),	"lappland"	)	
OR CONTAINS(LOWER([Result Title]),	"lapin lääni"	)	
OR CONTAINS(LOWER([Result Title]),	"norrbotten"	)	
THEN 'nordnorge and arctic'	

ELSEIF
CONTAINS(LOWER([Result Title]),	"barents sea"	)
OR CONTAINS(LOWER([Result Title]),	"barentshav"	)
OR CONTAINS(LOWER([Result Title]),	"petsjorahav"	)
OR CONTAINS(LOWER([Result Title]),	"pechora sea"	)
OR CONTAINS(LOWER([Result Title]),	"norwegian sea"	)
OR CONTAINS(LOWER([Result Title]),	"norske hav"	)
OR CONTAINS(LOWER([Result Title]),	"nordic sea"	)
OR CONTAINS(LOWER([Result Title]),	"ishav"	)
OR CONTAINS(LOWER([Result Title]),	"polhav" )
OR CONTAINS(LOWER([Result Title]),	"grønlandshav"	)
OR CONTAINS(LOWER([Result Title]),	"laptev sea"	)
OR CONTAINS(LOWER([Result Title]),	"kara sea"	)
OR CONTAINS(LOWER([Result Title]),	"fram strait"	)
OR CONTAINS(LOWER([Result Title]),	"yermak"	)
OR CONTAINS(LOWER([Result Title]),	"scotland ridge"	)
OR CONTAINS(LOWER([Result Title]),	"ægir ridge"	)
OR CONTAINS(LOWER([Result Title]),	"aegir ridge"	)
OR CONTAINS(LOWER([Result Title]),	"mohns ridge"	)
THEN 'nordnorge and arctic'		
		
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
THEN 'nordnorge and arctic'		

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
THEN 'nordnorge and arctic'

ELSEIF (		
CONTAINS(LOWER([Result Title]),	"northern norway"	)
OR CONTAINS(LOWER([Result Title]),	"nord-norge"	)
OR CONTAINS(LOWER([Result Title]),	"finnmark"	)
OR CONTAINS(LOWER([Result Title]),	"nordland"	)
OR REGEXP_MATCH(LOWER([Result Title]), "\btroms\b")
OR CONTAINS(LOWER([Result Title]),	"karasjok"	)
OR CONTAINS(LOWER([Result Title]),	"kautokeino"	)
OR CONTAINS(LOWER([Result Title]),	"hammarfest"	) 
OR CONTAINS(LOWER([Result Title]),	"vardø"	) 
OR CONTAINS(LOWER([Result Title]),	"vadsø"	) 
OR CONTAINS(LOWER([Result Title]),	"kirkenes"	)  
OR CONTAINS(LOWER([Result Title]),	"nordkapp"	) 
OR CONTAINS(LOWER([Result Title]),	"mo i rana"	) 
OR CONTAINS(LOWER([Result Title]),	"bodø"	) 
OR REGEXP_MATCH(LOWER([Result Title]), "\bbnarvik")
OR CONTAINS(LOWER([Result Title]),	"harstad"	) 
OR CONTAINS(LOWER([Result Title]),	"tromsø"	) 
OR REGEXP_MATCH(LOWER([Result Title]), "\balta\b")

OR CONTAINS(LOWER([Result Title]),	"northern sea route"	) 
OR CONTAINS(LOWER([Result Title]),	"arctic bridge"	) 
OR CONTAINS(LOWER([Result Title]),	"northeast passage"	) 
OR CONTAINS(LOWER([Result Title]),	"transpolar sea route"	) 
OR CONTAINS(LOWER([Result Title]),	"barents corridor"	) 
)			
THEN 'nordnorge and arctic'


// Book titles
ELSEIF		
REGEXP_MATCH(LOWER([result_title_anthology]), "\barctic") 
OR CONTAINS(LOWER([result_title_anthology]),	"arktisk"	)
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bpolar\b")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bpolare")
OR CONTAINS(LOWER([result_title_anthology]),	"polarforsk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polarsirke"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polarørken"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polarområde"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polarforsk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"circumpolar"	)
OR CONTAINS(LOWER([result_title_anthology]),	"north pole"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high north"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high-north"	)
OR CONTAINS(LOWER([result_title_anthology]),	"svalbard"	)
OR CONTAINS(LOWER([result_title_anthology]),	"spitsbergen"	)
OR CONTAINS(LOWER([result_title_anthology]),	"edgeøya"	)
OR CONTAINS(LOWER([result_title_anthology]),	"edge island"	)
OR CONTAINS(LOWER([result_title_anthology]),	"barentsøya"	)
OR CONTAINS(LOWER([result_title_anthology]),	"barents island"	)
OR CONTAINS(LOWER([result_title_anthology]),	"longyearbyen"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"bjornoy"	)
OR CONTAINS(LOWER([result_title_anthology]),	"bjørnøy"	)
OR CONTAINS(LOWER([result_title_anthology]),	"bear island"	)
OR CONTAINS(LOWER([result_title_anthology]),	"jan mayen"	)
OR CONTAINS(LOWER([result_title_anthology]),	"zemlya"	)
OR CONTAINS(LOWER([result_title_anthology]),	"novaja semlja"	)
OR CONTAINS(LOWER([result_title_anthology]),	"franz josef"	)
OR CONTAINS(LOWER([result_title_anthology]),	"frans josef"	)
OR CONTAINS(LOWER([result_title_anthology]),	"zemlja frantsa"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nordkalott"	)
OR CONTAINS(LOWER([result_title_anthology]),	"north calotte"	)
OR CONTAINS(LOWER([result_title_anthology]),	"greenland"	)
OR CONTAINS(LOWER([result_title_anthology]),	"grønland"	)	
	
OR CONTAINS(LOWER([result_title_anthology]),	"kola peninsula"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"murmansk"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"kolahalvøy"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"lapland"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"lappland"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"lapin lääni"	)	
OR CONTAINS(LOWER([result_title_anthology]),	"norrbotten"	)	
THEN 'nordnorge and arctic'	

ELSEIF
CONTAINS(LOWER([result_title_anthology]),	"barents sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"barentshav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"petsjorahav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"pechora sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"norwegian sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"norske hav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nordic sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ishav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polhav" )
OR CONTAINS(LOWER([result_title_anthology]),	"grønlandshav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"laptev sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"kara sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"fram strait"	)
OR CONTAINS(LOWER([result_title_anthology]),	"yermak"	)
OR CONTAINS(LOWER([result_title_anthology]),	"scotland ridge"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ægir ridge"	)
OR CONTAINS(LOWER([result_title_anthology]),	"aegir ridge"	)
OR CONTAINS(LOWER([result_title_anthology]),	"mohns ridge"	)
THEN 'nordnorge and arctic'		
		
ELSEIF		
CONTAINS(LOWER([result_title_anthology]),	"sea ice"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sea-ice"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice floe"	)
OR CONTAINS(LOWER([result_title_anthology]),	"pack ice"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polynya"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice stream"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice shelves"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice shelf"	)
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bnilas\b")
OR CONTAINS(LOWER([result_title_anthology]),	"ice chart"	)
OR CONTAINS(LOWER([result_title_anthology]),	"iceberg"	)
OR CONTAINS(LOWER([result_title_anthology]),	"slush"	)
OR CONTAINS(LOWER([result_title_anthology]),	"pancake ice"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ice ridge"	)
OR CONTAINS(LOWER([result_title_anthology]),	"permafrost"	)
OR CONTAINS(LOWER([result_title_anthology]),	"havis"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjøis"	)
OR CONTAINS(LOWER([result_title_anthology]),	"isberg")
OR CONTAINS(LOWER([result_title_anthology]),	"isfjell")
THEN 'nordnorge and arctic'		

ELSEIF (		
REGEXP_MATCH(LOWER([result_title_anthology]), "\bsami")
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bsamer\b")
OR CONTAINS(LOWER([result_title_anthology]),	"sámi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sápmi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"saami"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sjøsam"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nenets"	)
OR CONTAINS(LOWER([result_title_anthology]),	"khanty"	)
OR CONTAINS(LOWER([result_title_anthology]),	"evenk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"chukchi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"aleut"	)
OR CONTAINS(LOWER([result_title_anthology]),	"yupik "	)
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\binuit")
OR CONTAINS(LOWER([result_title_anthology]),	"kalaallit"	)
OR CONTAINS(LOWER([result_title_anthology]),	"inuvialuit"	)
)			
THEN 'nordnorge and arctic'

ELSEIF (		
CONTAINS(LOWER([result_title_anthology]),	"northern norway"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nord-norge"	)
OR CONTAINS(LOWER([result_title_anthology]),	"finnmark"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nordland"	)
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\btroms\b")
OR CONTAINS(LOWER([result_title_anthology]),	"karasjok"	)
OR CONTAINS(LOWER([result_title_anthology]),	"kautokeino"	)
OR CONTAINS(LOWER([result_title_anthology]),	"hammarfest"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"vardø"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"vadsø"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"kirkenes"	)  
OR CONTAINS(LOWER([result_title_anthology]),	"nordkapp"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"mo i rana"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"bodø"	) 
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\bbnarvik")
OR CONTAINS(LOWER([result_title_anthology]),	"harstad"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"tromsø"	) 
OR REGEXP_MATCH(LOWER([result_title_anthology]), "\balta\b")

OR CONTAINS(LOWER([result_title_anthology]),	"northern sea route"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"arctic bridge"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"northeast passage"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"transpolar sea route"	) 
OR CONTAINS(LOWER([result_title_anthology]),	"barents corridor"	) 
)			
THEN 'nordnorge and arctic'
```

## Search strategy - Web of Science

Search is designed for searching in Web of Science. Thus Norwegian terms are not included. 

The terms are grouped into sections:
- geographical/oceanic places
- arctic ice/sea ice
- artic/northern peoples
- northern Norway places
- arctic shipping routes

Some additional NOT terms may need to be combined with `polar` in the abstract search to avoid other uses of the word, e.g. polar acids, polar lipids. Less necessary with titles search.

An optional line is included at the end - broader, but can be used in certain situations.

```
TS=(
    "arctic" OR "polar" OR "north pole" OR "circumpolar" OR "high north" 

    OR "svalbard" OR "spitsbergen" OR "edge island" OR "edgeøya" OR "barentsøya" OR "barents island" OR "longyearbyen" OR "barentsburg"
    OR "bjornoy" OR "bjørnøy" OR "bear island" OR "jan mayen"
    OR "zemlya" OR "novaja semlja" OR "franz josef" OR "frans josef" OR "zemlja frantsa"

    OR "nordkalott" OR "north calotte" OR "greenland" OR "kola peninsula" OR "murmansk" OR "kolahalvøy" OR "lapland" OR "lapin lääni" OR "norrbotten"

    OR "barents sea*" OR "pechora sea*" OR "norwegian sea*" OR "nordic sea*" OR "iceland sea*" OR "nowegian basin"
    OR "laptev sea*" OR "kara sea*" OR "fram strait*" OR "yermak"
    OR "scotland ridge*" OR "aegir ridge" OR "ægir ridge" OR "mohns ridge"

    OR "sea ice" OR "sea-ice" OR "ice floe*" OR "pack ice" OR "polynya" OR "ice stream" OR "ice shelves" OR "ice shelf" OR "nilas" OR "ice chart*" OR "iceberg*" 
    OR "slush" OR "pancake ice" OR "ice ridge" OR "permafrost"

    OR "sami" OR "sapmi" OR "saami"
    
    OR "northern norw*" OR "north norw*" OR "finnmark" OR "nordland" OR "troms" OR "helgeland"
    OR "karasjok" OR "kautokeino" OR "hammarfest" OR "vardø" OR "vadsø" OR "kirkenes" OR "nordkapp" OR "mo i rana" OR "bodø" OR "lofoten" OR "narvik" OR "harstad" OR "tromsø" OR "alta" 

    OR "northern sea route*" OR "northeast passage*" OR "north-east passage*" OR "transpolar sea route*" OR "transpolar route*" OR "barents corridor*"

    OR 
        (
            ("norway" OR "norwegian" OR "nordic" OR "scandinavia*" OR "northern europe*") 
            AND ("subarctic" OR "offshore" OR "shipping" OR "vessel$" OR "sea lane*" OR "maritime" OR "subsea" OR "deep sea" OR "seafloor" OR "seabed")
        )
)		

```