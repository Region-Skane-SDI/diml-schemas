
# Diml klassdokumentation
Version 0.4.0

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
| rowSeparator | string | Nej |  |  | Anger vilket/vilka tecken som ska anv&#xE4;ndas som radavskiljare i utdatafilen, om filformatet &#xE4;r csv. |

## multiTableFileOutput
Anger en fil som inneh&#xE5;ller flera tabeller som output i definierat format (csv, parquet etc).

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## singleTableFileOutput
Anger en fil som output baserat p&#xE5; en tabell i definierat format (csv, parquet etc).

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| path | string | Ja |  |  | Anger filnamnet f&#xF6;r utdatafil |
| table | string | Ja |  |  | Anger k&#xE4;lltabell filen ska baseras p&#xE5; |

## apiOutput
Anger API som utdataformat enligt en angiven standard.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| apiOutputType | [apiOutputType](#apiOutputType) | Ja |  |  | Anger utdatatyper som &#xE4;r kompatibla med apiOutput. |
| channelId | string | Ja |  |  | API Id |

## dataInput
Anger en indatak&#xE4;lla f&#xF6;r en dataproduktsspecifikation, t.ex. en DataSource eller en annan DataProduct.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| channelId | string | Ja |  |  | Anger vilken typ av data som ska h&#xE4;mtas och i vilket format. |
| dimlId | dimlId | Ja |  |  | Ett globalt unikt dimlId f&#xF6;r indatak&#xE4;llan. |
| id | string | Ja |  |  | Ett id f&#xF6;r indatak&#xE4;llan. Detta m&#xE5;ste vara unikt inom en DataProduct d&#xE5; det kommer att anv&#xE4;ndas som ett alias. |

## conditionalDataType
Anv&#xE4;nds f&#xF6;r att evaluera vilken datatyp som ska tilldelas m&#xE5;lplattformen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| condition | string | Nej |  |  | Ett C#-uttryck som utv&#xE4;rderar huruvida den alternativa datatypen &#xE4;r den som ska tilldelas till m&#xE5;lplattformen. |
| dataType | string | Ja |  |  | Anger datatypen i m&#xE5;lplattformen. |

## dataTypeAttribute
Anv&#xE4;nds f&#xF6;r att definiera attribut som nyttjas i konverteringslogiken mellan Diml-datatyper och m&#xE5;lplattformar.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Anger ett namn som identifierar attributet. Detta v&#xE4;rde anv&#xE4;nds sedan i dimlAttributeSetting f&#xF6;r att tilldela ett v&#xE4;rde till attributet. |
| type | string | Ja |  |  | Anger attributets datatyp. |

## dataTypeAttributeSetting
Anv&#xE4;nds f&#xF6;r att tilldela v&#xE4;rden till dom attribut som definieras under dataTypes &gt; dimlAttributes.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| defaultValue | object | Nej |  |  | Anger ett standardv&#xE4;rde f&#xF6;r attributet. |
| id | string | Ja |  |  | Anger vilket attribut som ska anv&#xE4;ndas. Det som anges h&#xE4;r m&#xE5;ste matcha motsvarande attributs ID i &#x27;dataTypes&#x27; &gt; &#x27;dimlAttributes&#x27; &gt; &#x27;dimlAttribute&#x27; &gt; &#x27;id&#x27;. |

## dataTypes
Specificerar alla tillg&#xE4;ngliga Diml-datatyper samt konverteringslogiken mellan dess kompatibla m&#xE5;lplattformar, som t.ex. C#, TSQL och OpenAPI

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

## dimlDataType
Anger en Diml-datatyp baserat p&#xE5; dom typer som finns definierade i datatypsspecifikationen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## dimlDataTypeConfig
Anv&#xE4;nds f&#xF6;r att definiera datatyper i Diml.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| baseDataType | string | Nej |  |  | Anger vilken basdatatyp som datatypen &#xE4;rver fr&#xE5;n. |
| detectionPattern | string | Nej |  |  | Anger ett regulj&#xE4;rt uttryck som anv&#xE4;nds f&#xF6;r att identifiera datatypen. |
| detectionPriority | int32 | Nej |  |  | Anger en prioritetsordning f&#xF6;r det regulj&#xE4;ra uttrycket vid identifiering av datatypen. |
| id | string | Ja |  |  | Anger datatypens namn i Diml. |

## platformDataTypeConfig
Anger hur datatyperna konverteras fr&#xE5;n olika plattformar och format till Diml.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlDataType | string | Nej |  |  | Anger den aktuella datatypens namn i Diml |
| id | string | Ja |  |  | Anger den aktuella datatypen i m&#xE5;lplattformen |
| inputFormat | string | Ja |  |  | Anger ett regulj&#xE4;rt uttryck (REGEX) som matchar m&#xE5;lplattformens datatyp. |
| outputFormat | string | Nej |  |  | Anger vilket format m&#xE5;lplattformens datatyp skrivs ut i. |

## platformDataTypeParameter
&#xC4;nv&#xE4;nds f&#xF6;r att f&#xE5;nga parametrar fr&#xE5;n datatypsspecifikationens m&#xE5;lplattformar vid konvertering till Diml.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Anger id f&#xF6;r en parameter i m&#xE5;lplattformen baserat p&#xE5; regulj&#xE4;rt-uttryck i platFormDataTypeConfig -&gt; InputFormat. |
| inputExpression | string | Nej |  |  | Anger ett C#-uttryck som definierar hur parametern konverteras fr&#xE5;n standardv&#xE4;rdet &#x27;string&#x27; till det v&#xE4;rde som finns angivet i &#x27;type&#x27;. |
| type | string | Ja |  |  | Anger parameterns datatyp. |

## targetDataType
Anv&#xE4;nds f&#xF6;r att definiera konverteringslogiken fr&#xE5;n Diml-datatyp till en m&#xE5;lplattform.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dataType | string | Nej |  |  | Anger datatypen i m&#xE5;lplattformen. Kan inte anv&#xE4;ndas tillsammans med &#x27;conditionalDataType&#x27;. |
| platform | string | Ja |  |  | Anger vilken m&#xE5;lplattform som datatypen tillh&#xF6;r. |

## targetParameter
Tar olika inparametrar som anv&#xE4;nds f&#xF6;r olika typer av datak&#xE4;llor, t.ex databaser,filer eller api, till Diml och omv&#xE4;nt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Anger vilken parameter som ska anv&#xE4;ndas. |
| value | string | Ja |  |  | Ett C#-uttryck som anger v&#xE4;rdet f&#xF6;r parametern. |

## targetPlatform
Anger m&#xE5;lplattform f&#xF6;r datatypen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| platform | string | Ja |  |  | Anger vilken m&#xE5;lplattform som datatypen tillh&#xF6;r. |

## columnMapping
TODO

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| columnId | string | Ja |  |  | TODO |
| sourceColumnId | string | Ja |  |  | TODO |

## dataFlow
Anger fl&#xF6;det av data genom alla lager, samt egenskaper t.ex om en tabell ska materialiseras, uppdateras osv.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## dataIngest
Anger hur data ska inh&#xE4;mtas fr&#xE5;n k&#xE4;lla till destination.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| customSqlExpression | string | Nej |  |  | TODO |
| dataInputId | string | Ja |  |  | Ett unikt id som respesenterar en k&#xE4;lla. |
| id | string | Ja |  |  | Ett unikt id som representerar ett dataIngest-fl&#xF6;de. |

## dataProduct
Beskrivning av en dataprodukt med dess specifikationer.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |
| targetPlatform | [targetPlatformType](#targetPlatformType) | Ja |  |  | Anger vilken plattform som ska anv&#xE4;ndas. |

## dataSource
Beskrivning av en datak&#xE4;lla (som kan anv&#xE4;ndas av dataprodukter).

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

## dataStage
Anger de olika stadien f&#xF6;r data och dess egenskaper, tex. Om en tabell ska materialiseras eller inte, hur data ska uppdateras osv.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Unikt id f&#xF6;r dataStage. |
| materialization | [dataStageMaterialization](#dataStageMaterialization) | Ja |  |  | Anger om data ska materialiseras eller virtualiseras. |
| order | int32 | Ja |  |  | Anger ordningen p&#xE5; dataStage, dvs vilket steg som ska ske f&#xF6;rst. |
| role | [dataStageRole](#dataStageRole) | Nej |  |  | Anger vad som sker i dataStage. |

## dcat
Inneh&#xE5;ller egenskaper f&#xF6;r DCAT vilket &#xE4;r en metadataspecifikation f&#xF6;r att beskriva datam&#xE4;ngder. Mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dcatAccessRights | string | Ja |  |  | Anger vilka &#xE5;tkomstr&#xE4;ttigheter som finns f&#xF6;r dataprodukten i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.5 |
| dcatAvailability | string | Ja |  |  | Anger dataproduktens tillg&#xE4;nglighet i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.9 |
| dcatDataTheme | string | Ja |  |  | Anger vilket datatema dataprodukten tillh&#xF6;r i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.2 |
| dcatStatus | string | Ja |  |  | Anger dataproduktens status i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.8 |
| dcatUpdateFrequency | string | Ja |  |  | Anger dataproduktens uppdateringsfrekvens i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.4 |

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

## tableRelation
Anger eventuella tabellrelationer och hur de relaterar via relationsColumns.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id f&#xF6;r tabellrelationen. |
| targetTable | string | Ja |  |  | Anger vilken tabell som tabellrelationen relaterar till. |

## tableToTableMapping
TODO

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| allowSchemaDrift | boolean | Nej |  |  | TODO |
| customSqlExpression | string | Nej |  |  | TODO |
| sourceTableId | string | Ja |  |  | TODO |
| tableId | string | Ja |  |  | TODO |

## column
Beskriver en kolumn i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Kolumnens id. |

## columnAlias
Beskriver ett alias f&#xF6;r en kolumn i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| alias | string | Ja |  |  | Kolumnens alias. |
| stageId | string | Ja |  |  | Vilket steg aliaset skall g&#xE4;lla f&#xF6;r. |

## includeTable
Anger vilka tabeller som ska inkluderas i output.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar tabellen. |

## table
Beskriver en tabell i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Tabellens id. |

## tableAlias
Beskriver ett alias f&#xF6;r en tabell i en tabul&#xE4;r dataprodukt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| alias | string | Ja |  |  | Tabellens alias. |
| stageId | string | Ja |  |  | Vilket steg aliaset skall g&#xE4;lla f&#xF6;r. |

## dataSystemColumn
TODO: Saknar beskrivning.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar en data systemkolumn. |
| type | string | Ja |  |  | TODO: Saknar beskrivning. |

## description
Anv&#xE4;nds f&#xF6;r att beskriva ett Diml-objekt i olika format och spr&#xE5;k.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| language | string | Nej |  |  | Anger spr&#xE5;k f&#xF6;r beskrivning. |
| type | [descriptionType](#descriptionType) | Ja |  |  | Anger textformat f&#xF6;r beskrivningen |

## config
Konfiguration av Diml-milj&#xF6; d&#xE4;r t.ex standardspr&#xE5;k anges.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| defaultLanguage | string | Nej |  |  | Anger standardspr&#xE5;k f&#xF6;r en Diml-milj&#xF6; |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

## category
Anger kategorisering av dataprodukten t.ex namn, beskrivning och traits.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar kategorin. |

## graph
Anger ett grafobjekt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

## hierarchy
Definierar och beskriver hierarkier i Diml konfigfilen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

## list
Anger en lista.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | dimlId | Ja |  |  | En globalt unik identifierare f&#xF6;r Diml-objektet. |

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

## name
Anv&#xE4;nds f&#xF6;r att namnge ett Diml-objekt p&#xE5; olika spr&#xE5;k.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| language | string | Ja |  |  | En representation av vilket spr&#xE5;k som anv&#xE4;nds f&#xF6;r namnet. Exempelv&#xE4;rde: sv |

## tableToTableMappings
TODO

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |


## traitClass
Anger tillg&#xE4;ngliga klasser f&#xF6;r en Trait.

| Namn | Beskrivning |
| ---- | ----------- |
| category | Mappar till en kategori i DimlConfig. |
| columnSources | Anv&#xE4;nds f&#xF6;r att specificera k&#xE4;llan till en kolumn i en dataprodukt. |
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
| tableNamePrefix | Anv&#xE4;nds f&#xF6;r att specificera ett prefix f&#xF6;r alla tabellnamn i kotextet d&#xE4;r denna Trait anv&#xE4;nds. |
| tableNameSuffix | Anv&#xE4;nds f&#xF6;r att specificera ett suffix f&#xF6;r alla tabellnamn i kotextet d&#xE4;r denna Trait anv&#xE4;nds. |
| tableSchema | Anv&#xE4;nds f&#xF6;r att specificera ett schema f&#xF6;r alla tabeller i kotextet d&#xE4;r denna Trait anv&#xE4;nds. |
| tableUpdateType | Anger hur tabellen ska uppdateras. |
| targetUptimePercent | Anger en procentuell sats f&#xF6;r vilken tillg&#xE4;nglighet som avses att levereras. |

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
| sparql | SparkSQL. |
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

## dataStageMaterialization
Anger om data ska materialiseras eller virtualiseras.

| Namn | Beskrivning |
| ---- | ----------- |
| table | Anger om data ska sparas som en tabell. |
| view | Anger om data ska sparas som en vy. |

## dataStageRole
Anger vad som sker i dataStage.

| Namn | Beskrivning |
| ---- | ----------- |
| input | Data kommer in. |
| none | Inget. |
| output | Data g&#xE5;r ut. |
| transformation | Data transformeras enligt givna regler. |

## semanticLinkType
Anger hur andra produkter l&#xE4;nkar till varandra.

| Namn | Beskrivning |
| ---- | ----------- |
| has | Anger att en dataprodukt best&#xE5;r av en annan. |

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
| msFabric | Microsoft Fabric |
| sqlServer | SQL Server |


