## Get historical retail fuel price data

### Request the history data using getHistory API by symbol:

https://ondemand.websol.barchart.com/getHistory.json?apikey=YOUR_API_KEY&symbol=HOPA-516-1.CM&type=daily&startDate=20200501
```
{
    "status": {
        "code": 200,
        "message": "Success."
},
"results": [
    {
        "symbol": "HOPA-516-1.CM",
        "timestamp": "2020-05-01T00:00:00-04:00",
        "tradingDay": "2020-05-01",
        "open": 2.199,
        "high": 2.199,
        "low": 2.199,
        "close": 2.199,
        "volume": 0,
        "openInterest": null
},
...,
]}
```


