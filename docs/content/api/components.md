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
| results | [<code>Array&lt;FuelPricesByLocation&gt;</code>](#schemasFuelPricesByLocation) |  | false | A list of groups of fuel prices that are grouped by locations. |

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
| distance | <code>String</code> | false | true | Distance of the facility in miles from the input zip code or lat/lng. |
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
| symbol | <code>String</code> | true | false | A symbol or code that identifies a financial instrument. |
| name | <code>String</code> | true | false | The name of instrument. |
| dayCode | <code>String</code> | true | false | The day code for the session. Day codes are "1-9" for days 1 through 9, "0" (zero) for the 10th of the month, and "A - U" for days 11 through 31. |
| serverTimestamp | <code>String</code> | false | true | The time the message was generated on the server. |
| mode | <code>String</code> | true | true | An indicator representing if the quote is real-time ("R"), delayed ("I") or end-of-day ("D") if available. |
| lastPrice | <code>Number</code> | true | false | The last price the instrument traded. |
| tradeTimestamp | <code>String</code> | true | false | The exchange timestamp for the last traded price. |
| netChange | <code>Number</code> | true | false | The difference between the last traded price and the previous close. |
| percentChange | <code>Number</code> | true | true | The percent difference between the last traded price and the previous close. |
| unitCode | <code>String</code> | true | false | The corresponding unit code. |
| open | <code>Number</code> | true | false | The opening (first) price for the session. |
| high | <code>Number</code> | true | false | The highest traded price for the session. |
| low | <code>Number</code> | true | false | The lowest traded price for the session. |
| close | <code>Number</code> | true | true | The last traded price for the session. |
| numTrades | <code>Number</code>| true | false | The number of individual transactions over the course of a trading session. |
| dollarVolume | <code>Number</code>| true | true | The current Dollar Volume. |
| flag | <code>String</code> | true | false | If present, can be one of the following: "c" meaning that the market is closed for this instrument. "p" meaning that the market is in a pre-open state. This occurs when there are bids and offers being placed, but no trade has occurred yet. This is normally seen shortly before the official opening time for busy markets, but can also be seen throughout the day for lightly traded markets. "s" meaning that the instrument has settled, and that this is the final, settlement price. |
| volume | <code>Number</code> | true | false | The quantity of shares or contracts traded. |
| previousVolume | <code>Number</code>| true | false |The quantity of shares or contracts traded from the previous day. |

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
| symbol| <code>String</code> | true | false | A symbol or code that identifies a financial instrument. |
| timestamp | <code>String</code> | true | false | The exchange time of the price. Format: HH:MM:SS.FFF. |
| tradingDay | <code>String</code> | true | false |  The date of the trade. Format: YYYY-MM-DD.|
| open | <code>String</code> | true | true | The opening (first) price for the period. |
| high | <code>String</code> | true | true | The highest traded price for the period. |
| low | <code>String</code> | true | false | The lowest traded price for the period. |
| close | <code>String</code> | true | false | The last traded price for the period. |
| volume | <code>String</code> | true | false | The quantity of shares or contracts traded per the period. |
| openInterest | <code>String</code> | true | true | The total number of options and/or futures contracts that have not been offset. |

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


