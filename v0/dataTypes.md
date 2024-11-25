
# DimlDataTyper mappning dokumentation
Version 0.16.14




## DimlDatatyper
Används för att visa dimlDataTyper mappning till de olika platformar som datatypes filen stödjer.

| DimlDataTyper | default Attributes | T-SQL | .Net(C#) | Parquet | OpenAPI(Swagger) |
|-------------- | ------------------ | ----- | --------- | ------- | --------------- |
 | **string** |  length = 50&#xA;format = &#xA;isFixedLength = false&#xA;isWideChar = false&#xA;isNullable = false&#xA;  | Conditional datatypes: &#xA;&#xA;**nvarchar**  if (isWideChar == true &amp;&amp; isFixedLength == false) &#xA;. *Parameters:* (&#xA;length = length &gt; 0 ? length.ToString() : &quot;max&quot;). **char**  if (isWideChar == false &amp;&amp; isFixedLength == true) &#xA;. *Parameters:* (&#xA;length = length). **nchar**  if (isWideChar == true &amp;&amp; isFixedLength == true) &#xA;. *Parameters:* (&#xA;length = length). **varchar** &#xA;. *Parameters:* (&#xA;length = length &gt; 0 ? length.ToString() : &quot;max&quot;).  | Conditional datatypes: &#xA;&#xA;**char**  if (length == 1) &#xA;. *Parameters:* (&#xA;length = 1, isFixedLength = true). **string** | **STRING**&#xA;| **string**&#xA;format = format&#xA;| **string**&#xA;
  | **boolean** |  isNullable = false&#xA; | **bit**&#xA;| **bool**&#xA;| **BOOLEAN**&#xA;| **boolean**&#xA;| **boolean**&#xA;
  | **tinyInteger** |  unsigned = false&#xA;isNullable = false&#xA; | **tinyint**&#xA;unsigned = true&#xA; | Conditional datatypes: &#xA;&#xA;**sbyte**  if (unsigned == false) **byte** | **INT(8, &#x2B; !unsigned &#x2B;)**&#xA;| **integer**&#xA;format = int32&#xA;| **tinyint**&#xA;unsigned = false&#xA;
  | **smallInteger** |  unsigned = false&#xA;isNullable = false&#xA; | **smallint**&#xA; | Conditional datatypes: &#xA;&#xA;**short**  if (unsigned == false) **ushort** | **INT(16, &#x2B; !unsigned &#x2B;)**&#xA;| **integer**&#xA;format = int32&#xA;| **smallint**&#xA;unsigned = false&#xA;
  | **integer** |  unsigned = false&#xA;isNullable = false&#xA; | **int**&#xA; | Conditional datatypes: &#xA;&#xA;**int**  if (unsigned == false) **uint** | **INT(32, &#x2B; !unsigned &#x2B;)**&#xA;| **integer**&#xA;format = int32&#xA;| **int**&#xA;unsigned = false&#xA;
  | **bigInteger** |  unsigned = false&#xA;isNullable = false&#xA; | **bigint**&#xA; | Conditional datatypes: &#xA;&#xA;**long**  if (unsigned == false) **ulong** | **INT(64, &#x2B; !unsigned &#x2B;)**&#xA;| **integer**&#xA;format = int64&#xA;| **bigint**&#xA;unsigned = false&#xA;
  | **float** |  isNullable = false&#xA; | **real**&#xA;| **float**&#xA;| **FLAOT**&#xA;| **number**&#xA;format = float&#xA;| **float**&#xA;
  | **double** |  isNullable = false&#xA; | **float**&#xA;precision = precision&#xA;| **double**&#xA;| **DOUBLE**&#xA;| **number**&#xA;format = double&#xA;| **double**&#xA;
  | **decimal** |  precision = 19&#xA;scale = 4&#xA;isNullable = false&#xA;  | Conditional datatypes: &#xA;&#xA;**smallmoney**  if (precision == 10 &amp;&amp; scale == 4) &#xA;. *Parameters:* (&#xA;precision = precision, scale = scale). **money**  if (precision == 19 &amp;&amp; scale == 4) &#xA;. *Parameters:* (&#xA;precision = precision, scale = scale). **numeric** &#xA;. *Parameters:* (&#xA;precision = precision, scale = scale). | **decimal**&#xA;| **DECIMAL**&#xA;precision = precision&#xA;scale = scale&#xA;| **number**&#xA;| **decimal**&#xA;precision = precision&#xA;scale = scale&#xA;
  | **date** |  isNullable = false&#xA; | **date**&#xA;| **DateOnly**&#xA;| **DATE**&#xA;| **string**&#xA;format = date&#xA;| **date**&#xA;
  | **dateTime** |  precision = 0&#xA;isUtcTime = false&#xA;isNullable = false&#xA;  | Conditional datatypes: &#xA;&#xA;**datetime2** &#xA;. *Parameters:* (&#xA;precision = precision). | **DateTime**&#xA; | Conditional datatypes: &#xA;&#xA;**TIMESTAMP(&#x2B; isUtcTime &#x2B;, MILLIS)**  if (precision &lt;= 3) **TIMESTAMP(&#x2B; isUtcTime &#x2B;, MICROS)**  if (precision &lt;= 6) **TIMESTAMP(&#x2B; isUtcTime &#x2B;, NANOS)** | **string**&#xA;format = date-time&#xA;| **timestamp**&#xA;
  | **dateTimeOffset** |  precision = 0&#xA;isNullable = false&#xA; | **datetimeoffset**&#xA;precision = precision&#xA;| **DateTimeOffset**&#xA; | Conditional datatypes: &#xA;&#xA;**TIME(false, MILLIS)**  if (precision &lt;= 3) **TIME(false, MICROS)**  if (precision &lt;= 6) **TIME(false, NANOS)** | **string**&#xA;| **timestampOffset**&#xA;
  | **time** |  precision = 0&#xA;isUtcTime = false&#xA;isNullable = false&#xA; | **time**&#xA;precision = precision&#xA;| **TimeSpan**&#xA; | Conditional datatypes: &#xA;&#xA;**TIME(&#x2B; isUtcTime &#x2B;, MILLIS)**  if (precision &lt;= 3) **TIME(&#x2B; isUtcTime &#x2B;, MICROS)**  if (precision &lt;= 6) **TIME(&#x2B; isUtcTime &#x2B;, NANOS)** | **string**&#xA;| **string**&#xA;
  | **xml** |  isNullable = false&#xA; | **xml**&#xA;| **string**&#xA;| **string**&#xA;| **string**&#xA;| **string**&#xA;
  | **binary** |  length = 32&#xA;isFixedLength = false&#xA;isNullable = false&#xA;  | Conditional datatypes: &#xA;&#xA;**varbinary**  if (isFixedLength == true) &#xA;. *Parameters:* (&#xA;isFixedLength = true). **binary** &#xA;. *Parameters:* (&#xA;length = length, isFixedLength = false). | **byte[]**&#xA;| **BYTE_ARRAY**&#xA;| **string**&#xA;format = byte&#xA;| **binary**&#xA;
  | **guid** |  isNullable = false&#xA; | **binary**&#xA;length = 16&#xA;| **Guid**&#xA;| **UUID**&#xA;| **string**&#xA;format = uuid&#xA;| **string**&#xA;
  | **ssn** |  length = 12&#xA;format = \d{12}&#xA;isFixedLength = true&#xA;isNullable = false&#xA;  | Conditional datatypes: &#xA;&#xA;**nvarchar**  if (isWideChar == true &amp;&amp; isFixedLength == false) &#xA;. *Parameters:* (&#xA;length = length &gt; 0 ? length.ToString() : &quot;max&quot;). **char**  if (isWideChar == false &amp;&amp; isFixedLength == true) &#xA;. *Parameters:* (&#xA;length = length). **nchar**  if (isWideChar == true &amp;&amp; isFixedLength == true) &#xA;. *Parameters:* (&#xA;length = length). **varchar** &#xA;. *Parameters:* (&#xA;length = length &gt; 0 ? length.ToString() : &quot;max&quot;).  | Conditional datatypes: &#xA;&#xA;**char**  if (length == 1) &#xA;. *Parameters:* (&#xA;length = 1, isFixedLength = true). **string** | **STRING**&#xA;| **string**&#xA;format = format&#xA;| **string**&#xA;
  | **fullName** |    | Conditional datatypes: &#xA;&#xA;**nvarchar**  if (isWideChar == true &amp;&amp; isFixedLength == false) &#xA;. *Parameters:* (&#xA;length = length &gt; 0 ? length.ToString() : &quot;max&quot;). **char**  if (isWideChar == false &amp;&amp; isFixedLength == true) &#xA;. *Parameters:* (&#xA;length = length). **nchar**  if (isWideChar == true &amp;&amp; isFixedLength == true) &#xA;. *Parameters:* (&#xA;length = length). **varchar** &#xA;. *Parameters:* (&#xA;length = length &gt; 0 ? length.ToString() : &quot;max&quot;).  | Conditional datatypes: &#xA;&#xA;**char**  if (length == 1) &#xA;. *Parameters:* (&#xA;length = 1, isFixedLength = true). **string** | **STRING**&#xA;| **string**&#xA;format = format&#xA;| **string**&#xA;
  | **age** |   | **int**&#xA; | Conditional datatypes: &#xA;&#xA;**int**  if (unsigned == false) **uint** | **INT(32, &#x2B; !unsigned &#x2B;)**&#xA;| **integer**&#xA;format = int32&#xA;| **int**&#xA;unsigned = false&#xA;
 








## TSQL datatTyper:
Används för datatyp mappningen från TSQL platformen till dimldatatyper, visar också platformens parameterar samt detektionmösnter.
    
| TSQL DataTyp | DimlDataTyp | Plattform Parametrar | InputFormat |
| ------------- | ----------- | -------------------- | ----------- |
| varchar | string | length   | (?i)varchar\s*\((?&#x27;length&#x27;.*?)\) |
| nvarchar | string | length   | (?i)nvarchar\((?&#x27;length&#x27;.*?)\) |
| char | string | length   | (?i)char\((?&#x27;length&#x27;.*?)\) |
| nchar | string | length   | (?i)nchar\((?&#x27;length&#x27;.*?)\) |
| bit | boolean |  | bit |
| tinyint | tinyInteger |  | tinyint |
| smallint | smallInteger |  | smallint |
| int | integer |  | int |
| bigint | bigInteger |  | bigint |
| real | float |  | real |
| float |  ConditionalDataTypes:  Condition: precision == 7  **float**    Condition: precision == 15  **double**    **decimal** | precision   | (?i)float\s*\((?&#x27;precision&#x27;.*?)\) |
| smallmoney | decimal |  | smallmoney |
| money | decimal |  | smallmoney |
| decimal | decimal | precision  scale   | (?i)decimal\s*\((?&#x27;precision&#x27;.*?),\s*(?&#x27;scale&#x27;.*?)\) |
| numeric | decimal | precision  scale   | (?i)numeric\s*\((?&#x27;precision&#x27;.*?),\s*(?&#x27;scale&#x27;.*?)\) |
| date | date |  | date |
| smalldatetime | dateTime | precision   | (?i)smalldatetime\s*\((?&#x27;precision&#x27;.*?)\) |
| datetime | dateTime | precision   | (?i)datetime\s*\((?&#x27;precision&#x27;.*?)\) |
| datetime2 | dateTime | precision   | (?i)datetime2\s*\((?&#x27;precision&#x27;.*?)\) |
| datetimeoffset | dateTimeOffset | precision   | (?i)datetimeoffset\s*\((?&#x27;precision&#x27;.*?)\) |
| time | time | precision   | (?i)time\s*\((?&#x27;precision&#x27;.*?)\) |
| binary | binary | length   | (?i)binary\s*\((?&#x27;length&#x27;.*?)\) |
| varbinary | binary |  | varbinary |
| xml | xml |  | xml |
| uniqueidentifier | guid |  | uniqueidentifier |
| text | string | length   | text |
| ntext | string | length   | ntext |
| image | binary |  | image |

## CSHARP datatTyper:
Används för datatyp mappningen från CSHARP platformen till dimldatatyper, visar också platformens parameterar samt detektionmösnter.
    
| CSHARP DataTyp | DimlDataTyp | Plattform Parametrar | InputFormat |
| ------------- | ----------- | -------------------- | ----------- |
| char | string |  | char |
| string | string |  | string |
| bool | boolean |  | bool |
| sbyte | tinyInteger |  | sbyte |
| byte | tinyInteger |  | byte |
| short | smallInteger |  | short |
| ushort | smallInteger |  | ushort |
| int | integer |  | int |
| uint | integer |  | uint |
| long | bigInteger |  | long |
| ulong | bigInteger |  | ulong |
| float | float |  | float |
| double | double |  | double |
| decimal | decimal |  | decimal |
| DateOnly | date |  | DateOnly |
| DateTime | datetime |  | DateTime |
| DateTimeOffset | dateTimeOffset |  | DateTimeOffset |
| TimeSpan | time |  | TimeSpan |
| byte[] | binary |  | byte[] |

## PARQUET datatTyper:
Används för datatyp mappningen från PARQUET platformen till dimldatatyper, visar också platformens parameterar samt detektionmösnter.
    
| PARQUET DataTyp | DimlDataTyp | Plattform Parametrar | InputFormat |
| ------------- | ----------- | -------------------- | ----------- |
| STRING | string |  | STRING |
| ENUM | string |  | ENUM |
| UUID | guid |  | UUID |
| BOOLEAN | boolean |  | BOOLEAN |
| INT |  ConditionalDataTypes:  Condition: bitWidth == 8  **tinyInteger**    Condition: bitWidth == 16  **smallInteger**    Condition: bitWidth == 32  **integer**    **bigInteger** | bitWidth  isSigned   | (?i)INT\s*\((?&#x27;bitWidth&#x27;.*?),\s*(?&#x27;isSigned&#x27;.*?)\) |
| FLOAT | float |  | FLOAT |
| DOUBLE | double |  | DOUBLE |
| DECIMAL | decimal |  | DECIMAL |
| DATE | date |  | DATE |
| TIME | time | isAdjustedToUTC  unit   | (?i)TIME\s*\((?&#x27;isAdjustedToUTC&#x27;.*?),\s*(?&#x27;unit&#x27;.*?)\) |
| TIMESTAMP | timeStamp | isAdjustedToUTC  unit   | (?i)TIMESTAMP\s*\((?&#x27;isAdjustedToUTC&#x27;.*?),\s*(?&#x27;unit&#x27;.*?)\) |
| byte[] | binary |  | byte[] |
| JSON | string |  | JSON |
| UTF8 | string |  | UTF8 |
| INT_8 | tinyInteger |  | INT_8 |
| INT_16 | smallInteger |  | INT_16 |
| INT_32 | integer |  | INT_32 |
| INT_64 | bigInteger |  | INT_64 |
| UINT_8 | tinyInteger |  | UINT_8 |
| UINT_16 | smallInteger |  | UINT_16 |
| UINT_32 | integer |  | UINT_32 |
| UINT_64 | bigInteger |  | UINT_64 |
| TIME_MILLIS | time |  | TIME_MILLIS |
| TIME_MICROS | time |  | TIME_MICROS |
| TIMESTAMP_MILLIS | timeStamp |  | TIMESTAMP_MILLIS |
| TIMESTAMP_MICROS | timeStamp |  | TIMESTAMP_MICROS |

## OPENAPI datatTyper:
Används för datatyp mappningen från OPENAPI platformen till dimldatatyper, visar också platformens parameterar samt detektionmösnter.
    
| OPENAPI DataTyp | DimlDataTyp | Plattform Parametrar | InputFormat |
| ------------- | ----------- | -------------------- | ----------- |
| string |  ConditionalDataTypes:  Condition: format == &quot;date&quot;  **date**    Condition: format == &quot;date-time&quot;  **dateTime**    Condition: format == &quot;integer&quot;  **integer**    Condition: format == &quot;float&quot;  **float**    Condition: format == &quot;double&quot;  **double**    Condition: format == &quot;uuid&quot;  **guid**    **string** | format   | (?i)string\s*\((?&#x27;format&#x27;.*?)\) |
| number |  ConditionalDataTypes:  Condition: format == &quot;float&quot;  **float**    Condition: format == &quot;double&quot;  **double**    **decimal** | format   | (?i)number\s*\((?&#x27;format&#x27;.*?)\) |
| integer |  ConditionalDataTypes:  Condition: format == &quot;int64&quot;  **bigInteger**    **integer** | format   | (?i)integer\s*\((?&#x27;format&#x27;.*?)\) |
| boolean | boolean |  | boolean |

## SPARKSQL datatTyper:
Används för datatyp mappningen från SPARKSQL platformen till dimldatatyper, visar också platformens parameterar samt detektionmösnter.
    
| SPARKSQL DataTyp | DimlDataTyp | Plattform Parametrar | InputFormat |
| ------------- | ----------- | -------------------- | ----------- |
| string | string |  | string |
| boolean | boolean |  | boolean |
| tinyint | tinyInteger |  | tinyint |
| smallint | smallInteger |  | smallint |
| int | integer |  | int |
| bigint | bigInteger |  | bigint |
| float | float |  | float |
| double | double |  | double |
| decimal | decimal | precision  scale   | (?i)decimal\s*\((?&#x27;precision&#x27;[0-9]{1,2}),\s*(?&#x27;scale&#x27;[0-9]{1,2})\) |
| date | date |  | date |
| timestamp | dateTime |  | timestamp |
| timestampOffset | dateTimeOffset |  | string |
| binary | binary |  | binary |
| time | time |  | string |
