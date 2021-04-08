# Quick Start Guide

## Get an API key

If you'd like to use our service, please [visit our website](https://www.barchart.com/cmdty/data/retail-fuel-prices) and fill out the 'Get Started' form.  You can also send us an email at cmdty@barchart.com.  It's worth nothing that the more information you can provide us in the request will allow us to deliver a solution which best fits your needs.  Some information that would be helpful would include:
* Use Case - What are you looking to do with the information?
* Data Access - Is your application public or only available to subscribers?  Can users download the data?
* Historical Data - Do you require historical information or only current prices?
* Access Type - Do you want to see data for a zip code or for a collection of bids that you specify?

Once we have an understanding of what you're looking to do our team will be able to get you started.


## Making Your First Query

As an example, let's retrieve all retail fuel prices from all travel centers in your zip code area:
* Open your favorite web browserhttp://ondemand.websol.barchart.com/getFuelPrices.json?apikey={YOUR_API_KEY}&zipCode={YOUR_ZIP_CODE}
* Enter your API key and zip code into the url template:
* Copy and paste the url into the browser, and hit enter
* Voila! The API will returned qualified grain bids to your browser, similar to below:
```
"status": {
    "code": 200,
    "message": "Success."
    },
"results": [
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
    }]

## Explore More

Congrats! You've made your first query. Feel free to check more detailed documentation in our API Reference Section.  Here you can explore more advanced methods of querying grain prices data.
