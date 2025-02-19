
# Diml klassdokumentation
Diml version 2.0.0

## apiProduct
Beskrivning av en apiprodukt med dess specifikationer.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

## dataFlow
Anger fl&#xF6;det av data genom alla lager, samt egenskaper t.ex om en tabell ska materialiseras, uppdateras osv.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## dataIngest
Instruktioner f&#xF6;r hur data ska l&#xE4;sas in fr&#xE5;n k&#xE4;lla till destination.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| customSqlExpression | string | Nej |  |  | Ett SQL-uttryck som appliceras vid inl&#xE4;sning av data. |
| dataInputId | string | Ja |  |  | Ett unikt id som respesenterar en k&#xE4;lla. |
| id | string | Ja |  |  | Ett unikt id som representerar ett dataIngest-fl&#xF6;de. |

## dataInput
Anger en indatak&#xE4;lla f&#xF6;r en dataproduktsspecifikation, t.ex. en DataSource eller en annan DataProduct.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| channelId | string | Ja |  |  | Anger vilken typ av data som ska h&#xE4;mtas och i vilket format. |
| dimlId | dimlId | Ja |  |  | Ett globalt unikt dimlId f&#xF6;r indatak&#xE4;llan. |
| id | string | Ja |  |  | Ett id f&#xF6;r indatak&#xE4;llan. Detta m&#xE5;ste vara unikt inom en DataProduct d&#xE5; det kommer att anv&#xE4;ndas som ett alias. |

## dataProduct
Beskrivning av en dataprodukt med dess specifikationer.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |
| targetPlatform | [targetPlatformType](#targetPlatformType) | Ja |  |  | Anger vilken plattform som ska anv&#xE4;ndas. |
| uniqueName | string | Ja |  |  | Ett globalt unikt namn f&#xFFFD;r en dataspecifikation. |

## dataSource
Beskrivning av en datak&#xE4;lla (som kan anv&#xE4;ndas av dataprodukter).

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |
| sourcePlatform | [sourcePlatformType](#sourcePlatformType) | Ja |  |  | Anger vilken k&#xE4;llplattformstyp som ska anv&#xE4;ndas. |
| uniqueName | string | Ja |  |  | Ett globalt unikt namn f&#xFFFD;r en dataspecifikation. |

## dataStage
Anger de olika stadien f&#xF6;r data och dess egenskaper, tex. Om en tabell ska materialiseras eller inte, hur data ska uppdateras osv.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Unikt id f&#xF6;r dataStage. |
| materialization | [dataStageMaterialization](#dataStageMaterialization) | Ja |  |  | Anger om data ska materialiseras eller virtualiseras. |
| order | int32 | Ja |  |  | Anger ordningen p&#xE5; dataStage, dvs vilket steg som ska ske f&#xF6;rst. |
| role | [dataStageRole](#dataStageRole) | Nej |  |  | Anger vad som sker i dataStage. |
| type | [dataStageType](#dataStageType) | Ja |  |  | Anger vilken typ av dataStage . |

## dcat
Inneh&#xE5;ller egenskaper f&#xF6;r DCAT vilket &#xE4;r en metadataspecifikation f&#xF6;r att beskriva datam&#xE4;ngder. Mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dcatAccessRights | string | Ja |  |  | Anger vilka &#xE5;tkomstr&#xE4;ttigheter som finns f&#xF6;r dataprodukten i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.5 |
| dcatAvailability | string | Ja |  |  | Anger dataproduktens tillg&#xE4;nglighet i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.9 |
| dcatDataTheme | string | Ja |  |  | Anger vilket datatema dataprodukten tillh&#xF6;r i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.2 |
| dcatStatus | string | Ja |  |  | Anger dataproduktens status i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.8 |
| dcatUpdateFrequency | string | Ja |  |  | Anger dataproduktens uppdateringsfrekvens i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.4 |

## businessKey
Beskriver vilken kolumn som ska anv&#xE4;ndas som BusinessKey

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## columnMapping
En kolumnmappning mellan en k&#xE4;lla och en destination som anv&#xE4;nds vid datainl&#xE4;sning.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| columnId | string | Ja |  |  | Kolumnens id i destinationen. |
| sourceColumnId | string | Ja |  |  | Kolumnens id i k&#xE4;llan. |

## commonColumn
Beskriver en referens till en &#xE5;teranv&#xE4;ndbar kolumn.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Kolumnens id. |

## column
Beskriver en kolumn i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Kolumnens id. |

## table
Beskriver en tabell i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Tabellens id. |

## column
Beskriver en kolumn i en tabul&#xE4;r datak&#xE4;lla.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Kolumnens id. |

## table
Beskriver en tabell i en tabul&#xE4;r datak&#xE4;lla.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Tabellens id. |
| name | string | Ja |  |  | Tabellens namn. |
| schema | string | Ja |  |  | Tabellens schema. |

## includeTable
Anger vilka tabeller som ska inkluderas i output.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar tabellen. |

## logicColumnMapping
Beskriver hur kolumner ska transformeras.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| columnId | string | Ja |  |  | Anger kolumnid i tabellen. |
| customSqlExpression | string | Nej |  |  | Anger ett SQL-uttryck f&#xF6;r transformeringen. |
| trim | boolean | Nej |  |  | Anger om kolumnens v&#xE4;rden ska trimmas. |

## logicDataStageTable
Beskriver hur tabeller ska transformeras.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| filterSqlExpression | string | Nej |  |  | Anger om tabellrader ska filtreras. |
| tableId | string | Ja |  |  | Anger tabellid p&#xE5; tabell vars v&#xE4;rden ska transformeras. |
| trim | boolean | Nej |  |  | Anger om tabellens kolumnv&#xE4;rden ska trimmas om inte en specifik kolumn trim anges. |

## relationColumns
Anger med vilka kolumner en tabell relaterar till en annan.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| columnName | string | Ja |  |  | Anger relationkolumnens namn i k&#xE4;lltabellen. |
| targetColumnName | string | Ja |  |  | Anger relationkolumnens namn i den relaterade tabellen. |

## sampleDataRow
Anger exempeldata.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## tableInstance
Anger en instans av en tabell i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| alias | string | Ja |  |  | Anger tabellens alias f&#xF6;r ett eller flera dataStages. |
| fromStageId | string | Nej |  |  | Anger fr&#xE5;n och med vilket dataStage som tabellen ska byta namn i. Om inget anges g&#xE4;ller dataStage med order=&quot;1&quot;. |
| toStageId | string | Nej |  |  | Anger till och med vilket dataStage som tabellen ska byta namn i. Om inget anges g&#xE4;ller dataStage med order=&quot;X&quot;, d&#xE4;r X = h&#xF6;gsta order. |

## tableInstances
En samling av tabellinstanser i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| existsFromStageId | string | Nej |  |  | Anger fr&#xE5;n och med vilket dataStage som tabellen kommer att existera i. Om inget anges g&#xE4;ller dataStage med order=&quot;1&quot;. |
| existsToStageId | string | Nej |  |  | Anger till och med vilket dataStage som tabellen kommer att existera i. Om inget anges g&#xE4;ller dataStage med order=&quot;X&quot;, d&#xE4;r X = h&#xF6;gsta order. |

## tableRelation
Anger eventuella tabellrelationer och hur de relaterar via relationsColumns.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id f&#xF6;r tabellrelationen. |
| targetTableId | string | Ja |  |  | Anger vilken tabell som tabellrelationen relaterar till. |

## tableToTableMapping
En tabellmappning mellan en k&#xE4;lla och en destination som anv&#xE4;nds vid datainl&#xE4;sning.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| allowSchemaDrift | boolean | Nej |  |  | TODO |
| customSqlExpression | string | Nej |  |  | Ett SQL-uttryck som appliceras p&#xE5; tabellen vid inl&#xE4;sning. |
| sourceTableId | string | Ja |  |  | Tabellens id i k&#xE4;llan. |
| tableId | string | Ja |  |  | Tabellens id i destinationen. |

## customFormat
Beskriver ett egendefinierat utdataformat.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| customFormatId | string | Ja |  |  | Ett id f&#xF6;r det egendefinierade udataformatet. Id:et m&#xE5;ste vara unikt inom en dataproduktspecifikation d&#xE5; det kommer att anv&#xE4;ndas som ett alias. |
| formatType | [formatType](#formatType) | Ja |  |  | Anger kompatibla utdataformat. |
| mimeType | string | Nej |  |  | Anger en MIME-typ f&#xF6;r utdataformatet, om det &#xE4;r ett bin&#xE4;rformat. |
| schemaLocation | string | Nej |  |  | Anger ett schema f&#xF6;r utdataformatet. |

## sqlOutput
Anger output som SQL kod i angiven dialekt, tex: TSQL eller Spark SQL.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| channelId | string | Ja |  |  | Anger ett unikt id f&#xF6;r varje utkanaltyp t.ex sql,sql2 etc. |
| sqlOutputType | [sqlOutputType](#sqlOutputType) | Ja |  |  | Anger utdatatyper som &#xE4;r kompatibla med sqlOutput. |

## fileOutput
Anger en fil som destination f&#xF6;r utdata med ett antal obligatoriska parametrar.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| channelId | string | Ja |  |  | Anger ett unikt id f&#xF6;r varje utkanaltyp t.ex sql,sql2 etc. |
| columnSeparator | string | Nej |  |  | Anger vilket/vilka tecken som ska anv&#xE4;ndas som kolumnavskiljare i utdatafilen, om filformatet &#xE4;r csv. |
| customFormatId | string | Nej |  |  | Anger utdataformatet genom att referera till egendefinierat utdataformat i customFormats. |
| encoding | string | Nej |  |  | Teckenkodningen f&#xF6;r utdatafilen, t.ex. UTF-8. |
| fileFormat | [fileFormat](#fileFormat) | Ja |  |  | Anger kompatibla filformat. |
| path | string | Ja |  |  | S&#xF6;kv&#xE4;gen f&#xF6;r utdatafilen. |
| quoteCharacter | string | Nej |  |  | Anger vilket tecken som ska anv&#xE4;ndas som citationstecken i utdatafilen, om filformatet &#xE4;r csv. |
| rowSeparator | string | Nej |  |  | Anger vilket/vilka tecken som ska anv&#xE4;ndas som radavskiljare i utdatafilen, om filformatet &#xE4;r csv. |
| table | string | Nej |  |  | Anger vilken k&#xE4;lltabell som utdatafilen ska baseras p&#xE5;. |

## apiOutput
Anger API som utdataformat enligt en angiven standard.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| apiOutputType | [apiOutputType](#apiOutputType) | Ja |  |  | Anger utdatatyper som &#xE4;r kompatibla med apiOutput. |
| channelId | string | Ja |  |  | API Id |

## trait
Anv&#xE4;nds f&#xF6;r att specificera egenskaper (traits) p&#xE5; ett Diml-objekt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| class | [traitClass](#traitClass) | Ja |  |  | Anger tillg&#xE4;ngliga klasser f&#xF6;r en Trait. |
| subclass | string | Nej |  |  | Anger subtyp f&#xF6;r en Trait. |

## traitParameter
Anger v&#xE4;rden p&#xE5; en trait.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| key | string | Nej |  |  | Anger nyckelv&#xE4;rde f&#xF6;r traitParameter (default=value). |
| value | string | Nej |  |  | Anger v&#xE4;rde/v&#xE4;rden f&#xF6;r nyckeln. |

## name
Anv&#xE4;nds f&#xF6;r att namnge ett Diml-objekt p&#xE5; olika spr&#xE5;k.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| language | string | Ja |  |  | En representation av vilket spr&#xE5;k som anv&#xE4;nds f&#xF6;r namnet. Exempelv&#xE4;rde: sv |

## category
Anger kategorisering av dataprodukten t.ex namn, beskrivning och traits.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar kategorin. |

## commonColumnDefinition
Beskriver en kolumn som g&#xE5;r att &#xE5;teranv&#xE4;nda i flera tabeller.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Kolumnens id. |

## config
Konfiguration av Diml-milj&#xF6; d&#xE4;r t.ex standardspr&#xE5;k anges.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| defaultLanguage | string | Nej |  |  | Anger standardspr&#xE5;k f&#xF6;r en Diml-milj&#xF6; |

## graph
Anger ett grafobjekt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| configUrl | configUrl | Ja |  |  | En url till en konfigurationsfil f&#xF6;r Diml. |

## hierarchy
Definierar och beskriver hierarkier i Diml konfigfilen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| configUrl | configUrl | Ja |  |  | En url till en konfigurationsfil f&#xF6;r Diml. |

## list
Anger en lista.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| configUrl | configUrl | Ja |  |  | En url till en konfigurationsfil f&#xF6;r Diml. |

## listItem
Anger ett listobjekt inom en lista.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar ett list item. |

## node
Anger en nod inom ett grafobjekt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar en nod. |

## nodeLink
Anger hur noder inom ett grafobjekt relaterar till varandra.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar en nod-l&#xE4;nk. |
| targetNode | string | Ja |  |  | Anger m&#xE5;lnod som skall l&#xE4;nkas. |

## description
Anv&#xE4;nds f&#xF6;r att beskriva ett Diml-objekt i olika format och spr&#xE5;k.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| language | string | Nej |  |  | Anger spr&#xE5;k f&#xF6;r beskrivning. |
| type | [descriptionType](#descriptionType) | Ja |  |  | Anger textformat f&#xF6;r beskrivningen |

## dimlDataType
Anger en Diml-datatyp baserat p&#xE5; dom typer som finns definierade i datatypsspecifikationen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| bits | int32 | Nej |  |  | Anger antalet bitar som anv&#xE4;nds f&#xF6;r att lagra heltal. |
| format | dimlDataTypeFormat | Nej |  |  | Anger formatet p&#xE5; datan. T.ex. Xml eller Json. |
| id | [](#) | Ja |  |  |  |
| isFixedLength | boolean | Nej |  |  | Anger ifall t.ex. en str&#xE4;ng har en fixerad l&#xE4;ngd och alltid tar upp lika mycket plats. |
| isNullable | boolean | Nej |  |  | Anger ifall datatypen kan vara null eller ej. |
| isUnsigned | boolean | Nej |  |  | Anger ifall datatypen enbart kan inneh&#xE5;lla positiva heltal. |
| isWideChar | boolean | Nej |  |  | Anger ifall datatypen &#xE4;r en widechar is SQL. |
| length | int32 | Nej |  |  | Anger maxl&#xE4;ngden p&#xE5; t.ex. en str&#xE4;ng. |
| mantissa | int32 | Nej |  |  | Anger antalet bitar som anv&#xE4;nds f&#xF6;r att lagra mantissan f&#xF6;r flyttal. |
| originalDataType | string | Nej |  |  | Anger k&#xE4;llsystemets datatyp. |
| originalPlatform | string | Nej |  |  | Anger typen av k&#xE4;llsystem som datatypen h&#xE4;rstammar fr&#xE5;n. |
| precision | int32 | Nej |  |  | Anger precisionen f&#xF6;r tid och decimaltal. |
| scale | int32 | Nej |  |  | Anger skalan f&#xF6;r decimaltal. |

## columnInstance
Anger en instans av en kolumn i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| alias | string | Ja |  |  | Anger kolumnens alias f&#xF6;r ett eller flera dataStages. |
| fromStageId | string | Nej |  |  | Anger fr&#xE5;n och med vilket dataStage som kolumnen ska byta namn och/eller datatyp i. Om inget anges g&#xE4;ller dataStage med order=&quot;1&quot;. |
| toStageId | string | Nej |  |  | Anger till och med vilket dataStage som kolumnen ska byta namn och/eller datatyp i. Om inget anges g&#xE4;ller dataStage med order=&quot;X&quot;, d&#xE4;r X = h&#xF6;gsta order. |

## columnInstances
En samling av kolumninstanser i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| existsFromStageId | string | Nej |  |  | Anger fr&#xE5;n och med vilket dataStage som kolumnen ska existera i. Om inget anges g&#xE4;ller dataStage med order=&quot;1&quot;. |
| existsToStageId | string | Nej |  |  | Anger till och med vilket dataStage som kolumnen ska existera i. Om inget anges g&#xE4;ller dataStage med order=&quot;X&quot;, d&#xE4;r X = h&#xF6;gsta order. |


## dataStageMaterialization
Anger om data ska materialiseras eller virtualiseras.

| Namn | Beskrivning |
| ---- | ----------- |
| ingest | Ett specialfall som hanterar inl&#xE4;sning av data. Huruvida datat materialiseras i en tabell eller virtualiseras i en vy beror p&#xE5; vilken m&#xE5;lplattform som anv&#xE4;nds. |
| table | Anger att datat ska materialiseras i en tabell. |
| validate | Ett specialfall som hanterar validering av data. I det h&#xE4;r fallet materialiseras datat i en tabell och virtualiseras sedan i en vy d&#xE4;r eventuella filtreringar sker. |
| view | Anger att datat ska virtualiseras i en vy. |

## dataStageRole
Anger vad som sker i dataStage.

| Namn | Beskrivning |
| ---- | ----------- |
| control | Data kontrolleras enligt givna regler. |
| input | Data kommer in. |
| none | Inget. |
| output | Data g&#xE5;r ut. |
| transformation | Data transformeras enligt givna regler. |

## dataStageType
Anger vilken typ av dataStage .

| Namn | Beskrivning |
| ---- | ----------- |
| basicLogic |  |
| hash |  |
| ingestStore |  |
| logic |  |
| permaStore |  |
| tempStore |  |
| typecast |  |
| validate |  |

## semanticLinkType
Anger hur andra produkter l&#xE4;nkar till varandra.

| Namn | Beskrivning |
| ---- | ----------- |
| has | Anger att en dataprodukt best&#xE5;r av en annan. |

## sourcePlatformType
Anger vilken k&#xE4;llplattformstyp som ska anv&#xE4;ndas.

| Namn | Beskrivning |
| ---- | ----------- |
| azSqlServer | Azure SQL Server |
| sqlServer | SQL Server |

## formatType
Anger kompatibla utdataformat.

| Namn | Beskrivning |
| ---- | ----------- |
| binary | Bin&#xE4;rformat. |
| json | JSON-format. |
| xml | XML-format. |

## sqlOutputType
Anger utdatatyper som &#xE4;r kompatibla med sqlOutput.

| Namn | Beskrivning |
| ---- | ----------- |
| sparksql | SparkSQL. |
| tsql | T-SQL. |

## fileFormat
Anger kompatibla filformat.

| Namn | Beskrivning |
| ---- | ----------- |
| csv | CSV &#xE4;r ett vanligt textfilsformat f&#xF6;r att spara och &#xF6;verf&#xF6;ra tabelldata. |
| custom | Ett egendefinierat format. |
| parquet | Apache parquet &#xE4;r ett &#xF6;ppet k&#xE4;llkodsformat vilket &#xE4;r designat f&#xF6;r effektiv lagring och l&#xE4;sning. Mer information finns h&#xE4;r: (https://parquet.apache.org/).  |

## apiOutputType
Anger utdatatyper som &#xE4;r kompatibla med apiOutput.

| Namn | Beskrivning |
| ---- | ----------- |
| odata | ODATA. |

## traitClass
Anger tillg&#xE4;ngliga klasser f&#xF6;r en Trait.

| Namn | Beskrivning |
| ---- | ----------- |
| category | Mappar till en kategori i DimlConfig. |
| columnSources | Anv&#xE4;nds f&#xF6;r att specificera k&#xE4;llan till en kolumn i en dataprodukt. |
| dataStageOperations.applyDataQualityRules | Applicera definierade datakvalitetsregler |
| defaultConfigNamespace | Default konfiguration. |
| extension | Beskrivning saknas. |
| generateKeyHash | Genererar hashnyckel baserat p&#xE5; nyckelv&#xE4;rde. |
| generateRowHash | Genererar hash baserat p&#xE5; angivna kolumnv&#xE4;rden. Kan t.ex anv&#xE4;ndas vid merge f&#xF6;r att hitta f&#xF6;r&#xE4;ndringar snabbt. |
| guid | Beskrivning saknas. |
| icon | Anger en ikon f&#xF6;r en datak&#xE4;lla eller dataprodukt. Anv&#xE4;nds bland annat i datakatalogen. |
| infdom | Anv&#xE4;nds f&#xF6;r att beskriva informationsdom&#xE4;n f&#xF6;r en dataprodukt. |
| infoClass | Anger informationsklassning i f&#xF6;ljande format: K[X]R[X]T[X], d&#xE4;r X = [1-4]. |
| infomr | Anv&#xE4;nds f&#xF6;r att beskriva informationsomr&#xE5;de f&#xF6;r en dataprodukt. |
| isGreaterThan | Anv&#xE4;nds f&#xF6;r att beskriva att ett v&#xE4;rde &#xE4;r st&#xF6;rre &#xE4;n ett annat. |
| isUnlisted | Anger om en dataprodukt ska visas i datakatlogen eller inte. |
| isVirtual | Anger om en dataprodukt &#xE4;r virtuell. |
| pii | Anv&#xE4;nds f&#xF6;r att beskriva att det finns personuppgifter i kotextet d&#xE4;r denna Trait appliceras. |
| quality.businessKey.duplicate | Kontrollera dubletter p&#xE5; business key |
| quality.businessKey.null | Kontrollera ifall business key &#xE4;r null eller inte |
| quality.validate.action | Anger vilka &#xE5;tg&#xE4;rder som ska tas efter kvalitetskontroller i ett data stage av typen &#x27;validate&#x27; |
| tableNamePrefix | Anv&#xE4;nds f&#xF6;r att specificera ett prefix f&#xF6;r alla tabellnamn i kotextet d&#xE4;r denna Trait anv&#xE4;nds. |
| tableNameSuffix | Anv&#xE4;nds f&#xF6;r att specificera ett suffix f&#xF6;r alla tabellnamn i kotextet d&#xE4;r denna Trait anv&#xE4;nds. |
| tableSchema | Anv&#xE4;nds f&#xF6;r att specificera ett schema f&#xF6;r alla tabeller i kotextet d&#xE4;r denna Trait anv&#xE4;nds. |
| tableUpdateType | Anger hur tabellen ska uppdateras. |
| targetUptimePercent | Anger en procentuell sats f&#xF6;r vilken tillg&#xE4;nglighet som avses att levereras. |

## descriptionType
Anger textformat f&#xF6;r beskrivningen

| Namn | Beskrivning |
| ---- | ----------- |
| logicMd | Logic markdown format. |
| md | Markdown format. |
| plain | Plain text format. |

## targetPlatformType
Anger vilken plattform som ska anv&#xE4;ndas.

| Namn | Beskrivning |
| ---- | ----------- |
| azDatabricks | Azure Databricks |
| azSqlServer | Azure SQL Server |
| msFabricLakehouse | Microsoft Fabric Lakehouse |
| msFabricWarehouse | Microsoft Fabric Warehouse |
| sqlServer | SQL Server |

