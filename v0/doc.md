
# Diml klassdokumentation
Version 0.0.132

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
| dimlId | string | Ja |  |  | Ett globalt unikt dimlId f&#xF6;r indatak&#xE4;llan. |
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

## dimlDataType
Anger en Diml-datatyp baserat p&#xE5; dom typer som finns definierade i datatypsspecifikationen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |

## dimlDataTypeConfig
Anv&#xE4;nds f&#xF6;r att definiera datatyper i Diml.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| baseDataType | string | Nej |  |  | Anger vilken basdatatyp som datatypen &#xE4;rver fr&#xE5;n. |
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
| dataInputId | string | Ja |  |  | Ett unikt id som respesenterar en k&#xE4;lla. |
| id | string | Ja |  |  | Ett unikt id som representerar ett dataIngest-fl&#xF6;de. |

## dataProduct
Beskrivning av en dataprodukt med dess specifikationer.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | string | Ja |  |  | Dataproduktens dimlId (id). |

## dataSource
Beskrivning av en datak&#xE4;lla (som kan anv&#xE4;ndas av dataprodukter).

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | string | Ja |  |  | Datak&#xE4;llans DimlId (id). |

## dataStage
Anger de olika stadien f&#xF6;r data och dess egenskaper, tex. Om en tabell ska materialiseras eller inte, hur data ska uppdateras osv.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Unikt id f&#xF6;r dataStage. |
| materialization | [dataStageMaterialization](#dataStageMaterialization) | Ja |  |  | Anger om data ska materialiseras eller virtualiseras. |
| order | int32 | Ja |  |  | Anger ordningen p&#xE5; dataStage, dvs vilket steg som ska ske f&#xF6;rst. |
| role | [dataStageRole](#dataStageRole) | Nej |  |  | Anger vad som sker i dataStage. |

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

## dcat
Inneh&#xE5;ller egenskaper f&#xF6;r DCAT vilket &#xE4;r en metadataspecifikation f&#xF6;r att beskriva datam&#xE4;ngder. Mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dcatAccessRights | [dcatAccessRightsType](#dcatAccessRightsType) | Ja |  |  | Anger vilka &#xE5;tkomstr&#xE4;ttigheter som finns f&#xF6;r dataprodukten i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.5 |
| dcatAvailability | [dcatAvailabilityType](#dcatAvailabilityType) | Ja |  |  | Anger dataproduktens tillg&#xE4;nglighet i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.9 |
| dcatDataTheme | [dcatDataThemeType](#dcatDataThemeType) | Ja |  |  | Anger vilket datatema dataprodukten tillh&#xF6;r i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.2 |
| dcatStatus | [dcatStatusType](#dcatStatusType) | Ja |  |  | Anger dataproduktens status i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.8 |
| dcatUpdateFrequency | [dcatUpdateFrequencyType](#dcatUpdateFrequencyType) | Ja |  |  | Anger dataproduktens uppdateringsfrekvens i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.4 |

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

## category
Anger kategorisering av dataprodukten t.ex namn, beskrivning och traits.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| id | string | Ja |  |  | Ett unikt id som representerar kategorin. |

## graph
Anger ett grafobjekt.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | string | Ja |  |  | Ett unikt id som representerar en graf. |

## hierarchy
Definierar och beskriver hierarkier i Diml konfigfilen.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | string | Ja |  |  | Ett unikt DimlId som representerar hierarkin. |

## list
Anger en lista.

| Namn | Typ | Krävs | Defaultvärde | Ärvs från | Beskrivning |
| ---- | --- | ----- | ------------ | --------- | ----------- |
| dimlId | string | Ja |  |  | Ett unikt id som representerar en lista. |

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

## dcatAccessRightsType
Anger vilka &#xE5;tkomstr&#xE4;ttigheter som finns f&#xF6;r dataprodukten i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.5

| Namn | Beskrivning |
| ---- | ----------- |
| nonPublic | Inte tillg&#xE4;nglig f&#xF6;r allm&#xE4;nheten pga integritet, s&#xE4;kerhet eller andra orsaker. Anv&#xE4;ndningsanm&#xE4;rkning: Denna kategori kan omfatta resurser som inneh&#xE5;ller k&#xE4;nslig eller personlig information. |
| public | Tillg&#xE4;ngligt f&#xF6;r allm&#xE4;nheten. Anv&#xE4;ndningsanm&#xE4;rkning: Till&#xE5;tna hinder inkluderar registrering och beg&#xE4;ran av API-nycklar, s&#xE5; l&#xE4;nge vem som helst kan beg&#xE4;ra registrering och/eller API-nycklar. |
| restricted | Endast tillg&#xE4;ngligt under s&#xE4;rskilda villkor. Anv&#xE4;ndningsanm&#xE4;rkning: Denna kategori kan omfatta resurser som kr&#xE4;ver betalning, resurser som tillg&#xE4;ngligg&#xF6;rs inom ramen f&#xF6;r sekretessavtal, eller resurser d&#xE4;r utgivaren eller &#xE4;garen &#xE4;nnu inte har beslutat om de kan offentligg&#xF6;ras. |

## dcatAvailabilityType
Anger dataproduktens tillg&#xE4;nglighet i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.9

| Namn | Beskrivning |
| ---- | ----------- |
| available | Data finns tillg&#xE4;nglig f&#xF6;r n&#xE5;gra &#xE5;r, planering p&#xE5; medell&#xE5;ng sikt. |
| experimental | Data &#xE4;r tillg&#xE4;nglig p&#xE5; f&#xF6;rs&#xF6;k f&#xF6;r en kort period, kortsiktig planering. |
| stable | Data kommer att vara tillg&#xE4;nglig p&#xE5; l&#xE5;ng sikt. |
| temporary | Data kan f&#xF6;rsvinna n&#xE4;r som helst, ingen planering. |

## dcatDataThemeType
Anger vilket datatema dataprodukten tillh&#xF6;r i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.2

| Namn | Beskrivning |
| ---- | ----------- |
| econ | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som ekonomi eller finans. Ekonomi &#xE4;r omr&#xE5;det f&#xF6;r produktion, distribution och handel, samt konsumtion av varor och tj&#xE4;nster av olika agenter. I sin vidaste mening definieras ekonomin som en social dom&#xE4;n som betonar de praxis, diskurser och materiella uttryck som &#xE4;r f&#xF6;rknippade med produktion, anv&#xE4;ndning och f&#xF6;rvaltning av resurser. Finans &#xE4;r studiet av pengar och hur de anv&#xE4;nds. Specifikt handlar det om fr&#xE5;gorna om hur en individ, f&#xF6;retag eller regering skaffar de pengar som beh&#xF6;vs och hur de sedan spenderar eller investerar dessa pengar. Exempel p&#xE5; dataset: Tenders Electronic Daily (TED) - meddelanden om offentlig upphandling fr&#xE5;n EU och utanf&#xF6;r; Den offentliga sektorns underskott (-) och &#xF6;verskott (&#x2B;) - kvartalsdata. |
| educ | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som utbildning, kultur och sport. Utbildning &#xE4;r processen att underl&#xE4;tta l&#xE4;rande, eller f&#xF6;rv&#xE4;rvande av kunskap, f&#xE4;rdigheter, v&#xE4;rderingar, &#xF6;vertygelser och vanor. Kultur omfattar det sociala beteendet och de normer som finns i m&#xE4;nskliga samh&#xE4;llen, s&#xE5;v&#xE4;l som kunskap, &#xF6;vertygelser, konster, lagar, seder, f&#xF6;rm&#xE5;gor och vanor hos individerna i dessa grupper. Idrott omfattar alla former av t&#xE4;vlingsm&#xE4;ssig fysisk aktivitet eller spel som uppr&#xE4;tth&#xE5;ller eller f&#xF6;rb&#xE4;ttrar fysisk f&#xF6;rm&#xE5;ga och f&#xE4;rdigheter samtidigt som deltagarna njuter, och i vissa fall underh&#xE5;llning f&#xF6;r &#xE5;sk&#xE5;darna. Exempel p&#xE5; dataset: Europeiska f&#xE4;rdigheter, kompetenser, kvalifikationer och yrken (ESCO); EU:s medlemsstater och internationella &#xE5;taganden om m&#xE4;nskliga r&#xE4;ttigheter; Deltagande i kultur- eller sportaktiviteter under de senaste 12 m&#xE5;naderna efter k&#xF6;n, &#xE5;lder och utbildningsniv&#xE5;. |
| ener | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;nen energi. Energi &#xE4;r den kvantitativa egenskap som m&#xE5;ste &#xF6;verf&#xF6;ras till ett objekt f&#xF6;r att kunna utf&#xF6;ra arbete p&#xE5;, eller v&#xE4;rma, objektet. Levande organismer kr&#xE4;ver energi f&#xF6;r att h&#xE5;lla sig vid liv; m&#xE4;nsklig civilisation kr&#xE4;ver energi f&#xF6;r att fungera. Exempel p&#xE5; dataset: rapporter om den europeiska gasmarknaden; Elpriser efter typ av anv&#xE4;ndare. |
| envi | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;nen milj&#xF6;. Den naturliga milj&#xF6;n omfattar samspelet mellan alla levande arter, klimat, v&#xE4;der och naturresurser som p&#xE5;verkar m&#xE4;nniskans &#xF6;verlevnad och ekonomisk aktivitet. Exempel p&#xE5; dataset: EU-medborgarnas attityder till milj&#xF6;n; F&#xF6;roreningsutsl&#xE4;pp fr&#xE5;n transporter. |
| gove | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som regering eller offentlig sektor. En regering &#xE4;r systemet eller gruppen av m&#xE4;nniskor som styr ett organiserat samh&#xE4;lle, ofta en stat. Den offentliga sektorn &#xE4;r den del av ekonomin som best&#xE5;r av b&#xE5;de offentliga tj&#xE4;nster och offentliga f&#xF6;retag. Offentliga tj&#xE4;nster och f&#xF6;retag kan kontrolleras av statliga, regionala eller lokala myndigheter. Organisationer som inte ing&#xE5;r i den offentliga sektorn &#xE4;r antingen en del av den privata eller frivilliga sektorn. Exempel p&#xE5; dataset: Kandidatl&#xE4;nder och potentiella kandidater: Statistisk statistik; Transparensregister. |
| heal | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;nen h&#xE4;lsa. H&#xE4;lsa &#xE4;r ett tillst&#xE5;nd av fysiskt, psykiskt och socialt v&#xE4;lbefinnande d&#xE4;r sjukdom och handikapp saknas. Exempel p&#xE5; dataset: COVID-19 Coronavirus-data; Europeiska cancerinformationssystemet. |
| intr | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;nen f&#xF6;r internationella fr&#xE5;gor. En fr&#xE5;ga &#x2013; viktigt &#xE4;mne eller problem f&#xF6;r debatt eller diskussion &#x2013; &#xE4;r internationell n&#xE4;r deltagarna representerar minst tv&#xE5; l&#xE4;nder. Exempel p&#xE5; dataset: Konsoliderad lista &#xF6;ver personer, grupper och enheter som omfattas av EU:s ekonomiska sanktioner; Europeiska kommissionen &#x2013; GD DEVCO &#x2013; utveckling och humanit&#xE4;rt bist&#xE5;nd till Afghanistan. |
| just | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som r&#xE4;ttvisa, r&#xE4;ttssystem eller allm&#xE4;n s&#xE4;kerhet. R&#xE4;ttvisa inkluderar b&#xE5;de uppn&#xE5;endet av det som &#xE4;r r&#xE4;ttvist och den filosofiska diskussionen om det som &#xE4;r r&#xE4;ttvist; h&#xE4;r avses huvudsakligen den processuella r&#xE4;ttvisa som den finns i studien och till&#xE4;mpningen av lagen. V&#xE4;rldens samtida r&#xE4;ttssystem &#xE4;r i allm&#xE4;nhet baserade p&#xE5; ett av fyra grundl&#xE4;ggande system: civilr&#xE4;tt, sedvaner&#xE4;tt, lagstadgad lag, religi&#xF6;s lag eller kombinationer av dessa. Allm&#xE4;n s&#xE4;kerhet &#xE4;r en funktion av regeringar som s&#xE4;kerst&#xE4;ller skyddet av medborgare, personer p&#xE5; deras territorium, organisationer och institutioner mot hot mot deras v&#xE4;lbefinnande &#x2013; och v&#xE4;lst&#xE5;ndet i deras samh&#xE4;llen. Exempel p&#xE5; dataset: EU:s r&#xE4;ttspraxis; Information om medlemsstaternas lagstiftning; Europeiska datatillsynsmannens register &#xF6;ver behandlingar. |
| op_datpro | Saknar beskrivning. |
| regi | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som regioner eller st&#xE4;der. N&#xE4;r det g&#xE4;ller politisk geografi tenderar regioner att vara baserade p&#xE5; politiska enheter som suver&#xE4;na stater; subnationella enheter s&#xE5;som administrativa regioner, provinser, stater, grevskap, townships, territorier, etc.; och multinationella grupperingar. En stad &#xE4;r en stor m&#xE4;nsklig bos&#xE4;ttning. Exempel p&#xE5; dataset: NUTS - Nomenklatur f&#xF6;r territoriella enheter f&#xF6;r statistikklassificering; UDP - BNP per capita efter storstadsregioner, 2000 - 2060. |
| soci | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som befolkning eller samh&#xE4;lle. Befolkning &#xE4;r en samling av m&#xE4;nniskor och hela deras ras; det &#xE4;r antalet personer i en stad, region, ett land eller en v&#xE4;rld. Ett samh&#xE4;lle &#xE4;r en grupp individer som &#xE4;r involverade i ih&#xE5;llande social interaktion, eller en stor social grupp som delar samma rumsliga eller sociala territorium, vanligtvis f&#xF6;rem&#xE5;l f&#xF6;r samma politiska auktoritet och dominerande kulturella f&#xF6;rv&#xE4;ntningar. Exempel p&#xE5; dataset: Befolkningst&#xE4;thet efter NUTS 2-region; Violence against Women: En EU-omfattande unders&#xF6;kning. |
| tech | Detta koncept identifierar dataset som t&#xE4;cker dom&#xE4;ner som vetenskap eller teknik. Vetenskap &#xE4;r ett systematiskt f&#xF6;retag som bygger och organiserar kunskap i form av testbara f&#xF6;rklaringar och f&#xF6;ruts&#xE4;gelser. Modern vetenskap &#xE4;r typiskt indelad i tre huvudgrenar som best&#xE5;r av naturvetenskaperna, som studerar naturen i vid mening; samh&#xE4;llsvetenskaperna, som studerar individer och samh&#xE4;llen; och de formella vetenskaperna, som studerar abstrakta begrepp. Teknik &#xE4;r summan av tekniker, f&#xE4;rdigheter, metoder och processer som anv&#xE4;nds vid produktion av varor eller tj&#xE4;nster eller f&#xF6;r att uppn&#xE5; m&#xE5;l, s&#xE5;som vetenskaplig unders&#xF6;kning. Exempel p&#xE5; dataset: CORDIS - EU-forskningsprojekt under Horisont 2020 (2014&#x2013;2020); Uttag av mobilt bredband (abonnemang/100 personer). |
| tran | Detta koncept identifierar dataset som t&#xE4;cker transportdom&#xE4;nen. Transport &#xE4;r f&#xF6;rflyttning av m&#xE4;nniskor, djur och varor fr&#xE5;n en plats till en annan. Transports&#xE4;tt inkluderar luft, land (j&#xE4;rnv&#xE4;g och v&#xE4;g), vatten, kabel, r&#xF6;rledning och rymd. Exempel p&#xE5; dataset: Total l&#xE4;ngd p&#xE5; motorv&#xE4;gar; Flygplatstrafikdata genom att rapportera flygplats och flygbolag. |

## dcatStatusType
Anger dataproduktens status i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.8

| Namn | Beskrivning |
| ---- | ----------- |
| completed | Dataprodukten &#xE4;r f&#xE4;rdig. |
| deprecated | Dataprodukten &#xE4;r avvecklad. |
| underDevelopment | Dataprodukten &#xE4;r under utveckling. |
| withdrawn | Dataprodukten &#xE4;r tillbakadragen. |

## dcatUpdateFrequencyType
Anger dataproduktens uppdateringsfrekvens i datakatalogen. F&#xF6;ljer standarden DCAT-AP, mer information finns h&#xE4;r: https://docs.dataportal.se/dcat/en/#5.4

| Namn | Beskrivning |
| ---- | ----------- |
| annual | Uppdateras en g&#xE5;ng om &#xE5;ret. |
| annual2 | Uppdateras tv&#xE5; g&#xE5;nger om &#xE5;ret. |
| biennial | Uppdateras vartannat &#xE5;r. |
| bimonthly | Uppdateras varannan m&#xE5;nad. |
| biweekly | Uppdateras varannan vecka. |
| continuous | Uppdateras oftare &#xE4;n dagligen. |
| daily | Uppdateras en g&#xE5;ng om dagen. |
| daily2 | Uppdateras tv&#xE5; g&#xE5;nger om dagen. |
| irregular | Uppdateras med oj&#xE4;mna intervall. |
| monthly | Uppdateras en g&#xE5;ng i m&#xE5;naden. |
| monthly2 | Uppdateras tv&#xE5; g&#xE5;nger i m&#xE5;naden. |
| monthly3 | Uppdateras tre g&#xE5;nger i m&#xE5;naden. |
| other | Uppdateras med en annan typ av regelbundenhet (till exempel varje skott&#xE5;r). |
| quarterly | Uppdateras var tredje m&#xE5;nad. |
| triennial | Uppdateras vart tredje &#xE5;r. |
| unknown | Uppdateras med ok&#xE4;nd regelbundenhet. |
| update_Continuously | Uppdateras upprepningsvis utan avbrott. |
| weekly | Uppdateras en g&#xE5;ng i veckan. |
| weekly2 | Uppdateras tv&#xE5; g&#xE5;nger i veckan. |
| weekly3 | Uppdateras tre g&#xE5;nger i veckan. |

## descriptionType
Anger textformat f&#xF6;r beskrivningen

| Namn | Beskrivning |
| ---- | ----------- |
| logicMd | Logic markdown format. |
| md | Markdown format. |
| plain | Plain text format. |


