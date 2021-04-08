# Components

## Responses 

### Success :id=responsessuccess
> Success

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "Success.",
  "code": 200
}
```

* * *

### Unauthorized :id=responsesunauthorized
> The unauthorized access.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "API key is missing or not valid."
}
```

* * *

### BadRequest :id=responsesbadrequest
> The request was invalid, please see the message for more information.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": null,
  "code": 204
}
```

* * *

### ServerError :id=responsesservererror
> Something is not working correctly, please contact support.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "Something is not working correctly, please contact support.",
  "code": 500
}
```

* * *

## Schemas 

### GetFuelPricesResponse :id=schemasgetfuelpriceresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| results | [<code>Array&lt;FuelPricesByLocation&gt;</code>](#schemasFuelPricesByLocation) |  | false | A list of groups of grain bids that are grouped by locations. |

**Example**:

```json
{"results": [
    {"prices": [
        {"symbol": "HOPA-516-1.CM",
         "seriesName": "Pilot Flying J Des Moines, IA Diesel Price",
         "productId": 1,
         "product": "Diesel",
         "price": 3.099,
         "date": "2021-03-01"
        },
        {"symbol": "RBPA-516-4.CM",
         "seriesName": "Pilot Flying J Des Moines, IA Regular Gas Price",
         "productId": 4,
         "product": "Regular Gas",
         "price": 2.759,
         "date": "2021-03-01"
        },...],
     "distance": "27 miles away",
     "locationId": 516,
     "location": "Pilot Travel Center #373",
     "company": "Pilot Flying J",
     "address": "11957 Douglas Avenue",
     "highway": "I-35/80 Ext 126",
     "zipCode": "50322",
     "city": "Des Moines",
     "county": "Polk",
     "fipsCode": 19153,
     "state": "IA",
     "country": "USA",
     "longitude": -93.7808,
     "latitude": 41.63022,
     "phone": "515-276-1509",
     "showers": "17",
     "truckSpaces": "350",
     "weighScales": "CAT",
     "currency": "USD",
     "metric": "U.S. Customary Units",
     "locationUpdateDate": "2019-02-12",
     "lastUpdateTimestamp": "2021-04-07T00:00:00-05:00"
    }
  ]
}
```

* * *

### FuelPricesByLocation :id=schemasfuelpricesbylocation
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| prices | [<code>Array&lt;FuelPrice&gt;</code>](#schemasFuelPrice) |  | false | A list of prices from a travel center. Each price contains the meta and price data applicable to that location. |
| distance | <code>String</code> | false | true | Distance of the grain buying location in miles from the input zip code or lat/lng. |
| company | <code>String</code> | false | false | Name of the applicable travel center company. |
| locationId | <code>Integer</code> | false | false | A internal unique identifier of travel center. |
| location | <code>String</code> | false | false | Name of travel center that price originated from. |
| address | <code>String</code> | false | false | The street address of the location. |
| highway | <code>String</code> | false | false | The nearby highway exit(s). |
| zipCode | <code>String</code> | false | false | The zip code for the location. |
| city | <code>String</code> | false | false |The city for the location. |
| county | <code>String</code> | false | true | The county for the location.|
| fipsCode | <code>String</code> | false | true | A string concatenation of state FIPS code and county FIPS code to identify a county.|
| state | <code>String</code> | false | false | 2-char abbreviation of the state that contains the applicable fuel price. |
| country | <code>String</code> | false | false | ISO-3 country code of the location.|
| longitude | <code>Integer</code> | false | false | The longitude of the location. |
| latitude | <code>Integer</code> | false | false | The latitude of the location. |
| phone | <code>String</code> | false | true | The phone number for the location. |
| showers | <code>String</code> | false | true | The total number or availability of showers. |
| truckSpaces | <code>String</code> | false | true | The total number or availability of truck parking spaces. |
| weighScales | <code>String</code> | false | true | The brand or availability of weight scale. |
| currency | <code>String</code> | false | true | The currency used for the location.|
| metric | <code>String</code> | false | true | The units system a location used for quoting. |
| locationUpdateDate | <code>String</code> | false | false | Date when the meta data was last updated for a location in Central Time Zone.|
| lastUpdateTimestamp | <code>Integer</code> | false | false | Date that prices were last updated for a location in Central Time Zone.|

**Example**:

```json
{
   "prices": [
          {"symbol": "HOPA-516-1.CM",
           "seriesName": "Pilot Flying J Des Moines, IA Diesel Price",
           "productId": 1,
           "product": "Diesel",
           "price": 3.099,
           "date": "2021-03-01"
          },
          {"symbol": "RBPA-516-4.CM",
           "seriesName": "Pilot Flying J Des Moines, IA Regular Gas Price",
           "productId": 4,
           "product": "Regular Gas",
           "price": 2.759,
           "date": "2021-03-01"
          },...],
   "distance": "27 miles away",
   "locationId": 516,
   "location": "Pilot Travel Center #373",
   "company": "Pilot Flying J",
   "address": "11957 Douglas Avenue",
   "highway": "I-35/80 Ext 126",
   "zipCode": "50322",
   "city": "Des Moines",
   "county": "Polk",
   "fipsCode": 19153,
   "state": "IA",
   "country": "USA",
   "longitude": -93.7808,
   "latitude": 41.63022,
   "phone": "515-276-1509",
   "showers": "17",
   "truckSpaces": "350",
   "weighScales": "CAT",
   "currency": "USD",
   "metric": "U.S. Customary Units",
   "locationUpdateDate": "2019-02-12",
   "lastUpdateTimestamp": "2021-04-07T00:00:00-05:00"
    }
```

* * *

### FuelPrice :id=schemasfuelprice
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| symbol | <code>String</code> | false | true | The unique identifier of the price series. |
| seriesName | <code>String</code> | false | true | A short description of the price series. |
| productId | <code>Number</code> | false | true | A internal unique identifier for the product. |
| product | <code>String</code> | false | true | Name of the fuel product |
| price | <code>Number</code> | false | false | Spot price location to sell for the fuel product. |

**Example**:

```json
{
  "symbol": "HOPA-516-1.CM",
  "seriesName": "Pilot Flying J Des Moines, IA Diesel Price",
  "productId": 1,
  "product": "Diesel",
  "price": 3.099,
  "date": "2021-03-01"
}
```



### getQuoteResponse :id=schemasgetquoteresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| symbol | <code>String</code> | false | false |  |
| name | <code>String</code> | false | false |  |
| dayCode | <code>String</code> | false | false |  |
| serverTimestamp | <code>String</code> | false | true |  |
| mode | <code>String</code> | false | true |  |
| lastPrice | <code>Number</code> | false | false |  |
| tradeTimestamp | <code>String</code> | false | false |  |
| netChange | <code>Number</code> | false | false |  |
| percentChange | <code>Number</code> | false | true |  |
| unitCode | <code>String</code> | false | false |  |
| open | <code>Number</code> | false | false |  |
| high | <code>Number</code> | false | false |  |
| low | <code>Number</code> | false | true |  |
| close | <code>Number</code> | false | true |  |
| numTrades | <code>Number</code>| false | false |  |
| dollarVolume | <code>Number</code>| false | false |  |
| flag | <code>String</code> | false | true |  |
| volume | <code>Number</code> | false | false |  |
| previousVolume | <code>Number</code>| false | false |  |

**Example**:

```json
{
  "results": [
      {
          "symbol": "HOPA-516-1.CM",
          "name": "Pilot Des Moines, IA Diesel Price",
          "dayCode": "7",
          "serverTimestamp": "2021-04-08T09:35:32-05:00",
          "mode": "i",
          "lastPrice": 3.099,
          "tradeTimestamp": "2021-04-07T14:41:01-05:00",
          "netChange": -0.05999999999999961,
          "percentChange": -1.9,
          "unitCode": "3",
          "open": 3.099,
          "high": 3.099,
          "low": 3.099,
          "close": null,
          "numTrades": 1,
          "dollarVolume": null,
          "flag": "s",
          "volume": 0,
          "previousVolume": null
      }
  ]
}
```

* * *

### getHistoryResponse :id=schemasgethistoryresponse
**Type**: <code>Object</code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| symbol| <code>String</code> | true | false |  |
| timestamp | <code>String</code> | true | false |  |
| tradingDay | <code>String</code> | true | false |  |
| open | <code>String</code> | true | true |  |
| high | <code>String</code> | true | true |  |
| low | <code>String</code> | true | false |  |
| close | <code>String</code> | true | false |  |
| volume | <code>String</code> | true | false |  |
| openInterest | <code>String</code> | true | true |  |

**Example**:

```json
{
  "results": [
      {
          "symbol": "HOPA-516-1.CM",
          "timestamp": "2020-02-17T00:00:00-05:00",
          "tradingDay": "2020-02-17",
          "open": 2.759,
          "high": 2.759,
          "low": 2.759,
          "close": 2.759,
          "volume": 0,
          "openInterest": null
          },...,
      ]
}
```

* * *

## Security 

### JWT :id=securityjwt

>The JWT authorization

**Type**: http bearer
    
#### Headers
| Name | Format | Example |
| ---- | ------ | ------- |
| Authorization | JWT | Authorization: Bearer <code>&lt;Token&gt;</code> |

* * *

