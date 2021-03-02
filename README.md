# lib_Geocoding_Ngx
This is the geocoding library for Convertigo platform when network is reachable. Install this library to geocode coordinates for your Convertigo applications. It is based on Bing Maps location API. The shared component used in this library geocodes automatically browser's coordinates when network is reachable.

# Installation

* In your Convertigo Studio use File->Import->Convertigo->Convertigo Project and hit the 'Next' button

* In the Dialog 'Project remote URL' field Paste :

        lib_Geocoding_Ngx=https://github.com/convertigo/c8oprj-lib-geocoding-ngx.git

* And click the 'Finish' button
* Create all 'Undefined Global Symbols' when prompted

# Usage

## How to get your API Key

This library is based on severals locations API, to have this:

* [geo.api.gouv.fr](https://geo.api.gouv.fr/)
  * No needs any api key, (bust just working to find French locations )
* [Bing Maps](https://www.bingmapsportal.com/)
  * Go to https://www.bingmapsportal.com/ and sign in with your Microsoft account, if you don't have one, create one through the process
  * Go to "My Account" and click on "My Keys"
  * Fill out the form and click "Create" and get your API key details
  * Copy your API key

## Configuring Convertigo Symbols

__lib_Geocoding_Ngx__ needs some symbols to be configured. You configure them through the Web Console: **https://&lt;your site&gt;.convertigo.net/admin**, hit the ___symbols___ button to get to the symbol configuration page.

Symbol  | value
------| ------
lib_Geocoding_Ngx.provider | Can be "geo_api_gouv_fr" if you wants to use [geo.api.gouv.fr](https://geo.api.gouv.fr/) or "bings_map" if you wants to use [Bing Maps](https://www.bingmapsportal.com/)
lib_Geocoding_Ngx.BingsMapsApiKey.secret | Your **API key** value you copied from previous step if you choose [Bing Maps](https://www.bingmapsportal.com/)

## Sequences

__lib_Geocoding_Ngx__ provides sequences you can call in your projects

Sequence  | Action
------| ------
getGeocode | Return an object with human-readable address from coordinates. <br>Takes 3 variables :<br> - **point** : The coordinates of the location that you want to reverse geocode. A point is specified by a latitude and a longitude.<br >- **includeEntityTypes** : Specifies the entity types that you want to return in the response. Only the types you specify will be returned. If the point cannot be mapped to the entity types you specify, no location information is returned in the response.<br >

## Sample Application

* Allow access to your location from your browser when asked

You will find in this project a sample application using the geocoding library, use this as a reference and tutorial about using the library. This demonstrates :
- Use of the **getGeocode** Sequence
- Use of the **showAdress** parameter

## Shared component parameters

| Attribute        | Type           | Default | Description  |
| ------------- |-------------| -----|------------|
| showAddress      | Boolean | true    | Uses reverse geocoding to get a human-readable address |

## Shared Actions

### getCurrentPosition

This action is used to get the current position of the device. 

#### parameters
| Attribute        | Type           | Default | Description  |
| ------------- |-------------| -----|------------|
| **maximumAge**      | positive long | 0    | *Is a positive long value indicating the maximum age in milliseconds of a possible cached position that is acceptable to return. If set to 0, it means that the device cannot use a cached position and must attempt to retrieve the real current position. If set to Infinity the device must return a cached position regardless of its age. Default: 0.* |
| **timeout**      | positive long | Infinity    | *Is a positive long value representing the maximum length of time (in milliseconds) the device is allowed to take in order to return a position. The default value is Infinity, meaning that getCurrentPosition() won't return until the position is available.* |
| **enableHighAccuracy**      | Boolean | true    | *Is a Boolean that indicates the application would like to receive the best possible results. If true and if the device is able to provide a more accurate position, it will do so. Note that this can result in slower response times or increased power consumption (with a GPS chip on a mobile device for example). On the other hand, if false, the device can take the liberty to save resources by responding more quickly and/or using less power. Default: true.* |

#### Object returned
| Name        | Type           | Default 
| ------------- |-------------| -----|
| **latitude**      | double | *a double representing the position's latitude in decimal degrees.* |
| **longitude**      | double | *a double representing the position's longitude in decimal degrees.* |
| **altitude**      | double | *a double representing the position's altitude in meters, relative to sea level. This value can be null if the implementation cannot provide the data.* |
| **accuracy**      | double | *a double representing the accuracy of the latitude and longitude properties, expressed in meters.* |
| **altitudeAccuracy**      | double | *a double representing the accuracy of the altitude expressed in meters. This value can be null.* |
| **heading**      | double | *a double representing the direction towards which the device is facing. This value, specified in degrees, indicates how far off from heading true north the device is. 0 degrees represents true north, and the direction is determined clockwise (which means that east is 90 degrees and west is 270 degrees). If speed is 0, heading is NaN. If the device is unable to provide heading information, this value is null.*|
| **speed**      | double | *a double representing the velocity of the device in meters per second. This value can be null.*|


### getLocationByLatAndLong

This action is used to find a postion from latitude and longitude.

see: [bing maps documentation](https://docs.microsoft.com/en-us/bingmaps/rest-services/locations/find-a-location-by-point)

#### parameters
| Attribute        | Type           | Default | Description  |
| ------------- |-------------| -----|------------|
| **latitude**      | double |     | *a double representing the position's latitude in decimal degrees.* |
| **longitude**      | double |     | *a double representing the position's longitude in decimal degrees.* |
| **Address**      | boolean | true    | *define if you wants to include Address in the result* |
| **Postcode1**      | boolean | true    | *define if you wants to include Postcode in the result* |
| **CountryRegion**      | boolean |  true   | *define if you wants to include Country Region in the result* |
| **Neighborhood**      | boolean | false    | *define if you wants to include Neighborhood in the result* |
| **PopulatedPlace**      | boolean | false    | *define if you wants to include PopulatedPlace in the result* |
| **AdminDivision1**      | boolean | false    | *define if you wants to include AdminDivision1 in the result* |
| **AdminDivision2**      | boolean | false    | *define if you wants to include AdminDivision2 in the result* |

#### Object returned
| Name        | Type           | Default 
| ------------- |-------------| -----|
| **Address**      | Object | *contains result corresponding to specified parameters in request* |
| **BoundingBox**      | Object | *contains the bouding box of asked postion* |