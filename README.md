# FIRE5-Project

## XML-Schema (xsd-File)  
Filename: xsd_fire5_ccby4.xsd    
Enthält die Struktur des XML-Files.  


## Spezifikation  
Filename: spezifikation_fire5_ccby4.xlsx  
Enthält weitere Informationen zum Export, Benennung des exportierten Files, etc.  


## Datentypen
Es werden nur 3 Datentypen verwendet:   


|     Datentyp     |  Anzahl |        Kommentar      |
|:-----------------|--------:|:----------------------|
| xs:dateTime      |      36 | alle Daten als dateTime definieren     |
| xs:unsignedShort |       2 | dobyYear und deathYear |
| xs:string        |     145 | alle anderen                      |



## Prinzip eines Exports (delta- oder inkrementell Export)
SET @day_back := 1;   
SET @due_date := DATE_ADD(CURRENT_DATE, INTERVAL -@day_back DAY)   
SELECT patient_id, create_dt, change_dt, ...   
FROM db.entity   
WHERE create_dt >= @due_dt   
      OR change_dt >= @due_dt    
;	  



## Licence:                                                                                                                                              
FIRE5 © 2022 by Institute of Primary Care, University of Zurich and University Hospital Zurich, Zurich, Switzerland is licensed under CC BY 4.0.      
                                                                                                                                                      
To view a copy of this license, visit: http://creativecommons.org/licenses/by/4.0/    

