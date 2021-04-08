## Get today's retail fuel price quotes

You can use getFuelPrices API to request the most recent retail fuel price data.  The getFuelPrices API provides retail fuel price data and reference data.

Retail Fuel Price data can be requested for:
* Travel center locations
* Geographic coordinates and radius
* Zip code and radius 
* A specified county

Looking for something more specific? Retail Fuel Price data can be filtered by product name,  and by the number of locations that will be returned.

Reference data contains travel center locations and product standard names, which provides valid values in use for requesting fuel price data.

Reference data can be requested for geographic coordinates and radius. If no geographic coordinates are given, reference data will return all valid values by default.

See examples in below answers.



## Get a list of active locations

An active location is defined as a travel center that has at least one active retail fuel price.

You can pull all active locations by using the getFuelPrices API with input parameter “requestType=locations”:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey=[YOUR_API_KEY]&requestType=locations

## Get a list of product names

You can pull all supported product names by using getFuelPrices API with input parameter “requestType=products”:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey=[YOUR_API_KEY]&requestType=products

## Get retail fuel prices for the specified area
An area can be defined by geographic coordinates and radius, by zip code and radius, and by county fips code, and by county name.

Get all fuel prices for an area defined by lat&lng and maxDistance:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey=YOUR_API_KEY&latitude=41.00189&longitude=-83.325035&maxDistance=20

Get all fuel prices for up to closet 50 locations within an area defined by zipCode and maxDistance:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey= YOUR_API_KEY&zipCode=43351&maxDistance=50&totalLocations=50

Get all fuel prices for a county by fips code:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey=YOUR_API_KEY&fipsCode=39175

Get all fuel prices for a county by county name:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey=YOUR_API_KEY&county=Wyandot-OH

## Get retail fuel prices for specified products:
You can filter the retail fuel prices by product via adding input “productName=[product_name]“. Heads up, product_name needs to be encoded.

Get all Midgrade Gasoline prices for up to closet 50 locations within an area defined by zipCode and maxDistance:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey= YOUR_API_KEY&zipCode=43351&maxDistance=50&totalLocations=50&productName=Midgrade%20Gas


## Get retail fuel prices from specified location(s)
Get all fuel prices for specified locationIds:

http://ondemand.websol.barchart.com/getFuelPrices.json?apikey=YOUR_API_KEY&location=579,744
