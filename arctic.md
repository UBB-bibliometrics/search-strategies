# Arctic research search string

## Scope
All research publications related to the arctic in the last 10 years. We include "polar" even though this may relate to the south pole too. 

## Search strategy - Tableau

Superfluous terms (such as `greenland sea` when `greenland` is included) are removed. 

```
// Journals
IF CONTAINS(LOWER([journal]),	"arctic"	)
OR CONTAINS(LOWER([journal]),	"circumpolar"	)
OR REGEXP_MATCH([journal], "\bpolar\b")
THEN 'arctic'		
			
ELSEIF		
CONTAINS(LOWER([result_title]),	"barents sea"	)
OR CONTAINS(LOWER([result_title]),	"greenland sea"	)
OR CONTAINS(LOWER([result_title]),	"norwegian sea"	)
OR CONTAINS(LOWER([result_title]),	"nordic seas"	)
OR CONTAINS(LOWER([result_title]),	"arctic sea"	)
OR CONTAINS(LOWER([result_title]),	"ishav"	)
OR CONTAINS(LOWER([result_title]),	"chukchi sea"	)
OR CONTAINS(LOWER([result_title]),	"east Siberian sea"	)
OR CONTAINS(LOWER([result_title]),	"laptev sea"	)
OR CONTAINS(LOWER([result_title]),	"kara sea"	)
OR CONTAINS(LOWER([result_title]),	"labroador sea"	)
OR CONTAINS(LOWER([result_title]),	"Greenland sea"	)
OR CONTAINS(LOWER([result_title]),	"Beaufort sea"	)
OR CONTAINS(LOWER([result_title]),	"Sea of Okhotsk"	)
OR CONTAINS(LOWER([result_title]),	"weddell sea"	)
OR CONTAINS(LOWER([result_title]),	"ross sea"	)
OR CONTAINS(LOWER([result_title]),	"hudson bay"	)
OR CONTAINS(LOWER([result_title]),	"drake passage"	)
OR CONTAINS(LOWER([result_title]),	"bering strait"	)
OR CONTAINS(LOWER([result_title]),	"davis strait"	)
OR CONTAINS(LOWER([result_title]),	"nares strait"	)
OR CONTAINS(LOWER([result_title]),	"jan mayen"	)
OR CONTAINS(LOWER([result_title]),	"scotland ridge"	)
OR CONTAINS(LOWER([result_title]),	"greenland basin"	)
OR CONTAINS(LOWER([result_title]),	"arctic water"	)
OR CONTAINS(LOWER([result_title]),	"polar water"	)
OR CONTAINS(LOWER([result_title]),	"arctic current"	)
OR CONTAINS(LOWER([result_title]),	"polar current"	)
THEN 'arctic'		
		
ELSEIF		
CONTAINS(LOWER([result_title]),	"sea ice"	)
OR CONTAINS(LOWER([result_title]),	"sea-ice"	)
OR CONTAINS(LOWER([result_title]),	"ice floe"	)
OR CONTAINS(LOWER([result_title]),	"pack ice"	)
OR CONTAINS(LOWER([result_title]),	"polynya"	)
OR CONTAINS(LOWER([result_title]),	"ice stream"	)
OR CONTAINS(LOWER([result_title]),	"ice shelves"	)
OR CONTAINS(LOWER([result_title]),	"ice shelf"	)
OR REGEXP_MATCH([result_title], "\bnilas\b")
OR CONTAINS(LOWER([result_title]),	"ice chart"	)
OR CONTAINS(LOWER([result_title]),	"iceberg"	)
OR CONTAINS(LOWER([result_title]),	"slush"	)
OR CONTAINS(LOWER([result_title]),	"pancake ice"	)
OR CONTAINS(LOWER([result_title]),	"ice ridge"	)
OR CONTAINS(LOWER([result_title]),	"havis"	)
OR CONTAINS(LOWER([result_title]),	"sjøis"	)
OR CONTAINS(LOWER([result_title]),	"isberg"	)
THEN 'arctic'		
		
ELSEIF (		
CONTAINS(LOWER([result_title]),	"arctic"	)
OR CONTAINS(LOWER([result_title]),	"arktisk"	)
OR CONTAINS(LOWER([result_title]),	"north pole"	)
OR CONTAINS(LOWER([result_title]),	"circumpolar"	)
OR CONTAINS(LOWER([result_title]),	"polarforsk"	)
OR REGEXP_MATCH([result_title], "\bpolar\b")
OR CONTAINS(LOWER([result_title]),	"high north"	)
OR CONTAINS(LOWER([result_title]),	"high-north"	)
OR CONTAINS(LOWER([result_title]),	"svalbard"	)
OR CONTAINS(LOWER([result_title]),	"spitsbergen"	)
OR CONTAINS(LOWER([result_title]),	"bjornoy"	)
OR CONTAINS(LOWER([result_title]),	"bjørnøy"	)
OR CONTAINS(LOWER([result_title]),	"jan mayan"	)
OR CONTAINS(LOWER([result_title]),	"greenland"	)
OR CONTAINS(LOWER([result_title]),	"north alaska"	)
OR CONTAINS(LOWER([result_title]),	"northern quebec"	)
OR CONTAINS(LOWER([result_title]),	"axel heiberg"	)
OR CONTAINS(LOWER([result_title]),	"north slope"	)
OR CONTAINS(LOWER([result_title]),	"prudhoe"	)
OR CONTAINS(LOWER([result_title]),	"barrow"	)
OR CONTAINS(LOWER([result_title]),	"zemlya"	)
OR CONTAINS(LOWER([result_title]),	"yermak"	)
OR CONTAINS(LOWER([result_title]),	"franz josef"	)
OR CONTAINS(LOWER([result_title]),	"northwest territories"	)
OR CONTAINS(LOWER([result_title]),	"high latitude"	)
OR CONTAINS(LOWER([result_title]),	"high-latitude"	)
OR CONTAINS(LOWER([result_title]),	"south pole"	)
)			
THEN 'arctic'	

ELSEIF (		
CONTAINS(LOWER([result_title]),	"sami"	)
OR CONTAINS(LOWER([result_title]),	"sámi"	)
OR CONTAINS(LOWER([result_title]),	"sápmi"	)
OR CONTAINS(LOWER([result_title]),	"saami"	)
OR CONTAINS(LOWER([result_title]),	"nenets"	)
OR CONTAINS(LOWER([result_title]),	"khanty"	)
OR CONTAINS(LOWER([result_title]),	"evenk"	)
OR CONTAINS(LOWER([result_title]),	"chukchi"	)
OR CONTAINS(LOWER([result_title]),	"aleut"	)
OR CONTAINS(LOWER([result_title]),	"yupik "	)
OR REGEXP_MATCH([result_title], "\binuit")
OR CONTAINS(LOWER([result_title]),	"kalaallit"	)
OR CONTAINS(LOWER([result_title]),	"inuvialuit"	)
)			
THEN 'arctic'

// Book titles
ELSEIF (
CONTAINS(LOWER([result_title_anthology]),	"barents sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"greenland sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"norwegian sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nordic seas"	)
OR CONTAINS(LOWER([result_title_anthology]),	"skager"	)
OR CONTAINS(LOWER([result_title_anthology]),	"arctic sea"	)
OR CONTAINS(LOWER([result_title_anthology]),	"ishav"	)
OR CONTAINS(LOWER([result_title_anthology]),	"jan mayen"	)				
OR CONTAINS(LOWER([result_title_anthology]),	"arctic water"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polar water"	)
)			
THEN 'arctic'	

ELSEIF		
CONTAINS(LOWER([result_title_anthology]),	"arctic"	)
OR CONTAINS(LOWER([result_title_anthology]),	"arktisk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"north pole"	)
OR CONTAINS(LOWER([result_title_anthology]),	"circumpolar"	)
OR CONTAINS(LOWER([result_title_anthology]),	"polarforsk"	)
OR REGEXP_MATCH([result_title_anthology], "\bpolar\b")
OR CONTAINS(LOWER([result_title_anthology]),	"high north"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high-north"	)
OR CONTAINS(LOWER([result_title_anthology]),	"svalbard"	)
OR CONTAINS(LOWER([result_title_anthology]),	"spitsbergen"	)
OR CONTAINS(LOWER([result_title_anthology]),	"greenland"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high latitude"	)
OR CONTAINS(LOWER([result_title_anthology]),	"high-latitude"	)
OR CONTAINS(LOWER([result_title_anthology]),	"south pole"	)
THEN 'arctic'		

ELSEIF (		
CONTAINS(LOWER([result_title_anthology]),	"sami"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sámi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"sápmi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"saami"	)
OR CONTAINS(LOWER([result_title_anthology]),	"nenets"	)
OR CONTAINS(LOWER([result_title_anthology]),	"khanty"	)
OR CONTAINS(LOWER([result_title_anthology]),	"evenk"	)
OR CONTAINS(LOWER([result_title_anthology]),	"chukchi"	)
OR CONTAINS(LOWER([result_title_anthology]),	"aleut"	)
OR CONTAINS(LOWER([result_title_anthology]),	"yupik "	)
OR REGEXP_MATCH([result_title_anthology], "\binuit")
OR CONTAINS(LOWER([result_title_anthology]),	"kalaallit"	)
OR CONTAINS(LOWER([result_title_anthology]),	"inuvialuit"	)
)			
THEN 'arctic'		
		
ELSE "non"
END
```
