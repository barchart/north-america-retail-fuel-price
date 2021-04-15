# Paths

## GET /getFuelPrices

> The getFuelPrices API provides refined fuel price data and reference data. Refined fuel data can be requested for fuel selling locations, for geographic coordinates and radius, for zip code and radius, and for a specified county. Refined fuel data can be filtered by product name(s), and by number of locations will be returned. Reference data contains fuel selling locations and product names, providing valid values in use for requesting refined fuel data. Reference data can be requested for geographic coordinates and radius. If no geographic coordinates are given, reference data will return all valid values by default.

**Summary**: Resturns a list of fuel prices grouped by locations.

#### Query Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key |
| requestType | <code>String</code> | false | false | The type of request that is being requested in order to determine the type of data to be returned. Valid Values:"products", "locations", "prices" . Default Value: "prices"<br> |
| location | <code>Array</code> | false | false | A location id or a code identifies a or multiple fuel selling location(s) that fuel prices will be returned for. A valid code consist of multiple location ids separated by a comma, and the code can contain up to 100 locations. A list of valid location ids can be retrieved by using this API with input: requestType = location. location and several other inputs -geographic coordinates, zipCode, maxDistance, county, totalLocations- are mutually exclusive.
| latitude | <code>Number</code> | false | false | The latitude of a valid geographic coordinates to define the center of area that fuel prices will be returned for. The `latitude` Must be used together with `longitude`. Geographic coordinates and Zipcode are mutually exclusive.<br> |
| longitude | <code>Number</code> | false | false | The longitude of a valid geographic coordinates to define the center of area that fuel prices will be returned for. Geographic coordinates and Zipcode are mutually exclusive.<br> |
| zipCode | <code>Integer</code> | false | false | A valid US or Canadian zip code to define the area that fuel prices orginate from. Default Value: 60606 `zipCode` and Geographic coordinates  are mutually exclusive.<br> |
| maxDistance | <code>Integer</code> | false | false | The maximum distance from searched zipcode or the requested geo coordinates in miles. This input helps to define the area that fuel prices will be returned from. Default value is 100. Maximum value is 250.<br> |
| county | <code>String</code> | false | false | A valid string code which represents the concatenation of county name and state code seperated by a hyphen.<br> |
| fipsCode | <code>Integer</code> | false | false | A concatenation of state FIPS code and county FIPS code without separator to define the county that fuel prices will be returned for. A list of possible values can be found at (here)[https://www.nass.usda.gov/Data_and_Statistics/County_Data_Files/Frequently_Asked_Questions/county_list.txt].<br> |
| productName | <code>String</code> | false | false | A standard commodity name or a name list that separated by pipe sign to filter fuel prices. Note that the input need to be encoded in UTF-8. A list of valid commodity names can be retrieved by using this API with input: requestType = commodities.<br> |
| totalLocations | <code>Integer</code> | false | false | The maximum amount of fuel selling locations that fuel prices will be returned for. If zip code is set, then API will provide cashbid for given amount closet locations in relation to the requested zip code. Maximum value is 100.<br> |
| page | <code>Integer</code> | false | false | The page number.<br> |
| fields | <code>String</code> | false | false | Additional as per-requested fields that the user can define. Requested fields should be separated by a comma. Valid per-requested fields are "companyId", "locationType", "mailingAddress", "fax", "defLanes", "dieselLanes", "bioBlend", "businessHours", "productId", "productShort", "productFull"<br> |

#### Responses

**Status Code**: 200

> OK

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetFuelPricesResponse&gt;</code>](/content/api/components?id=schemasgetfuelpriceresponse)

* * *

**Status Code**: 400

> Bad Request

* * *

**Status Code**: 500

> Internal Server Error


* * *

## GET /getQuote 

> The getQuote API is used to request price data by symbol on stocks, indexes, mutual funds, ETFs, futures, foreign exchange, cryptocurrencies, or commodity cash data.

**Summary**: Retrieve today's fuel prices by symbol(s).

#### Query Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key. |
| symbols | <code>String</code> | true | false | A symbol or code that identifies a financial instrument. Multiple symbols separated by a comma may be used. For futures, notation such as for the active contract or for the first nearby is supported, as is for all futures contracts for a given root symbol, as is for all options contracts for a given underlying futures symbol. |
| fields | <code>String</code> | false | true | The fields requested. Valid fields can be found in [getQuoteResponse](/content/api/components?id=schemasgetquoteresponse.|
| only | <code>String</code> | false | true | Returns only specified fields, i.e. symbol,name. |


#### Responses

**Status Code**: 200

> A JSON document, containing an array of quote objects.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetQuoteResponse&gt;</code>](/content/api/components?id=schemasgetquoteresponse)

* * *

**Status Code**: 500

> A JSON document, containing an error.

**Content Type**: <code>application/json</code>

**Response Type:** <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "string"
}
```

* * *

## GET /getHistory 

> The getHistory API is used to request historical time series data on stocks, indexes, mutual funds, ETFs, futures, foreign exchange, cryptocurrencies, or cash commodity data. Historical data is available as tick, minute bars or end-of-day data.

**Summary**: Retrieve historical retail fuel prices.

#### Path Parameters

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| apikey | <code>String</code> | true | false | The authorized API Key |
| symbol | <code>String</code> | true | false | A symbol or code that identifies a financial instrument.|
| type | <code>String</code> | false | true | The type of historical data to return, including tick data, minute data, and end-of-day data.|
| startDate | <code>String</code> | false | true | The start date of the historical data query. This parameter should be set to the desired start date/time for the query (the result set will include records back to, and including, this value). If not set, the value will default to the beginning of the day specified in the end parameter, if end is specified, or to the beginning of the current day, if end is not specified. The value should conform to the format yyyymmdd[hhmm[ss]], where fields in brackets are optional (Do not include the brackets themselves). Any optional fields that are not explicitly set will default to 0 (i.e. 20090203 will default to 20090203000000).|
| endDate | <code>String</code> | false | true | The end data of the historical data query. This parameter should be set to the desired end date/time for the query (the result set will include records up to, but not including, this value). If not set, the value will default to the end of the day specified in the start parameter, if specified, or to the end of the current day, if start is not specified. The value should conform to the format yyyymmdd[hhmm[ss]], where fields in brackets are optional (Do not include the brackets themselves). Any optional fields that are not explicitly set will default to 0 (i.e. 20090203 will default to 20090203000000). |
| maxRecords | <code>String</code> | false | true | The maximum amount of records returned. This parameter should be set to the maximum number of records desired. If not specified, there number of records returned will be determined by the date/time parameters specified as well as any defaults that apply to the query. |
| order | <code>String</code> | false | true | An arrangement of fields within a particular record (ascending or descending). This parameter can be set to one of two values ("asc" and "desc") in order to specify the chronological order of the result set returned. If this parameter is not specified, the order results is not guaranteed. |


#### Responses

**Status Code**: 200

> A JSON document, containing an array of alert objects.

**Content Type**: <code>application/json</code>

**Response Type:** [<code>Array&lt;GetHistoryResponse&gt;</code>](/content/api/components?id=schemasgethistoryresponse)

* * *

**Status Code**: 500

> A JSON document, containing an error.

**Content Type**: <code>application/json</code>

**Response Type:** <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "string"
}
```

* * *

