# Weather Observed
This entity contains a harmonised description of the weather at a particular location and time. This entity is primarily associated with the vertical segments of the environment and agriculture but is applicable to many different applications.

| Attribute Name | Attribute Type | Description | Constraint |
|:--- |:--- |:--- |:---:|
| id | @id | Provides a unique identifier for an instance of the entity either in the form of a URI (i.e. either a publicly accessible URL or a URN). | Mandatory |
| type | @type | Defines the type of the entity. | Mandatory |
| createdAt | DateTime | Indicates the date/ time that the instance of the entity was created in ISO 8601 format. The value of this will be set by the server when the entity was created. | Mandatory |
| modifiedAt | DateTime | Indicates the date/ time when the entity was last modified in ISO 8601 format. The value of this will be set by the server when the entity was modified, if the entity has not been modified it may have a null value. | Optional |
| source | Property | Specifies the URL to the source of this data (either organisation or where relevant more specific source) | Recommended |
| dataProvider | Property | Specifies the URL to information about the provider of this information | Recommended |
| entityVersion | Property | The entity specification version as a number. A version number of 2.0 or later denotes the entity is represented using NGSI-LD | Recommended |
| name | Property | The name of the weather observation location. | Optional |
| location | GeoProperty | The geo location (point/ polygon) of this weather observation. | Mandatory |
| POI | Relationship | A reference to the Point of Interest (i.e. monitoring station) that this observation was reported from. | Recommended |
| stationCode | Property | The station code for the weather monitoring device/ station. | Optional |
| devices | Relationship | Reference to the IoT devices (i.e. sensors) which generated the weather observations. | Recommended |
| observedAt | TemporalProperty | Indicates the date/time the observation was observed by the associated meteorological agency. | Mandatory |
| weatherType | Property | The weather type. A choice from an enumerated list. One of: **notAvailable, clearNight, sunnyDay, partlyCloudy, mist, fog, cloudy, overcast, lightRainShower, drizzle, lightRain, heavy RainShower, heavyRain, sleetShower, sleet, hailShower, hail, lightSnow Shower, lightSnow, heavySnowShower,heavySnow, thunderShower, thunder.** | Recommended |
| visibility | Property | Defines the observed visibility nominally in metres or in an alternative measurement according to specified unitCode | Recommended |
| address | Property | The weather forecast location encoded as a Schema.org PostalAddress. https://schema.org/PostalAddress | Recommended |
| temperature | Property | The temperature expressed in degrees Celsius. | Recommended |
| windDirection | Property | The wind direction expressed in degrees compared to geographic North (measured clockwise). | Recommended |
| windSpeed | Property | The forecasted wind speed in meters per second. | Recommended |
| relativeHumidity | Property | The relative humidity expressed a number between\n\n0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100% | Recommended |
| dewPoint | Property | The dew point expressed in degrees Celsius. | Optional |
| atmosphericPressure | Property | The measured barometric or atmospheric pressure in units of hecto Pascals. | Recommended |
| pressureTendency | Property | Indicates the change in atomospheric pressure. A choice from an enumerated list: **rising, falling, steady** | Recommended |
| rainRate | Property | The current rate of precipitation nominally in milli litres per hour | Recommended |
| rainFall | Property | Is the accumulated rain as is defined in the station (since rain started, since day started, since month started). referencePeriod enumerates the basis - one of **rainStart, dayStart, monthStart** | Recommended |
| evapoTranspiration | Property | The sum of evaporation and plant transpiration from the Earth's land and ocean surface to the atmosphere. | Recommended |
| referenceEvapoTranspiration | Property | Environmental demand for evapotranspiration. Represents the evapotranspiration rate of a short green crop (grass), completely shading the ground, of uniform height and with adequate water status in the soil profile | Recommended |

## NGSI-LD Context Definition
The following NGSI-LD context definition applies to the **Weather Observed** entity

[Download context definition.](../examples/Weather-Observed-context.jsonld)

```JavaScript
{
    "source": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/source",
        "@type": "Property"
    },
    "dataProvider": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dataprovider",
        "@type": "Property"
    },
    "entityVersion": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/entityversion",
        "@type": "Property"
    },
    "POI": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/poi",
        "@type": "Relationship"
    },
    "stationCode": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/stationcode",
        "@type": "Property"
    },
    "devices": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/devices",
        "@type": "Relationship"
    },
    "weatherType": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/weathertype",
        "@type": "Property"
    },
    "visibility": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/visibility",
        "@type": "Property"
    },
    "address": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/address",
        "@type": "Property"
    },
    "temperature": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/temperature",
        "@type": "Property"
    },
    "windDirection": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/winddirection",
        "@type": "Property"
    },
    "windSpeed": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/windspeed",
        "@type": "Property"
    },
    "relativeHumidity": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/relativehumidity",
        "@type": "Property"
    },
    "dewPoint": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dewpoint",
        "@type": "Property"
    },
    "atmosphericPressure": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/atmosphericpressure",
        "@type": "Property"
    },
    "pressureTendency": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/pressuretendency",
        "@type": "Property"
    },
    "rainRate": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/rainrate",
        "@type": "Property"
    },
    "rainFall": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/rainfall",
        "@type": "Property"
    },
    "evapoTranspiration": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/evapotranspiration",
        "@type": "Property"
    },
    "referenceEvapoTranspiration": {
        "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/referenceevapotranspiration",
        "@type": "Property"
    }
}
```
## Example of Weather Observed Entity
The following is an example instance of the **Weather Observed** entity

[Download example entity definition.](../examples/Weather-Observed.jsonld)

```JavaScript
{
    "@context": [
        "https://forge.etsi.org/gitlab/NGSI-LD/NGSI-LD/raw/master/coreContext/ngsi-ld-core-context.json",
        "https://raw.githubusercontent.com/GSMADeveloper/NGSI-LD-Entities/master/examples/Weather-Observed-context.jsonld"
    ],
    "id": "urn:ngsi-ld:WeatherObserved:adb144fb-e732-4944-a192-8690bd17de8c",
    "type": "WeatherObserved",
    "createdAt": "2017-01-01T01:20:00Z",
    "modifiedAt": "2017-05-04T12:30:00Z",
    "source": "https://source.example.com",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "name": {
        "type": "Property",
        "value": "London City"
    },
    "location": {
        "type": "GeoProperty",
        "value": {
            "type": "Point",
            "coordinates": [
                -104.99404,
                39.75621
            ]
        }
    },
    "POI": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:POI:b16f4666-5a6b-11e8-be71-3b0aa1fc6248"
    },
    "stationCode": {
        "type": "Property",
        "value": "LCW100"
    },
    "devices": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:Device:4514d07a-59ae-11e8-8d8d-8fb340a9451f",
            "urn:ngsi-ld:Device:4bdbd926-59ae-11e8-a29d-1f6336c78c14",
            "urn:ngsi-ld:Device:52890d20-59ae-11e8-8449-ef9315a0a3ca",
            "urn:ngsi-ld:581fc4e0-59ae-11e8-99fe-17206cbbcec7"
        ]
    },
    "observedAt": {
        "type": "TemporalProperty",
        "value": "2017-05-04T10:18:16Z"
    },
    "weatherType": {
        "type": "Property",
        "value": "sunnyDay"
    },
    "visibility": {
        "type": "Property",
        "value": 1500,
        "unitCode": "MTR"
    },
    "address": {
        "type": "Property",
        "addressLocality": "London",
        "postalCode": "EC4N 8AF",
        "streetAddress": "25 Walbrook"
    },
    "temperature": {
        "type": "Property",
        "value": 30,
        "unitCode": "CEL"
    },
    "windDirection": {
        "type": "Property",
        "value": 122,
        "unitCode": "DD"
    },
    "windSpeed": {
        "type": "Property",
        "value": 3,
        "unitCode": "MTS"
    },
    "relativeHumidity": {
        "type": "Property",
        "value": 0.1,
        "unitCode": "C62"
    },
    "dewPoint": {
        "type": "Property",
        "value": 10,
        "unitCode": "CEL"
    },
    "atmosphericPressure": {
        "type": "Property",
        "value": 10,
        "unitCode": "CEL"
    },
    "pressureTendency": {
        "type": "Property",
        "value": 10
    },
    "rainRate": {
        "type": "Property",
        "value": 10,
        "unitText": "ml/h"
    },
    "rainFall": {
        "type": "Property",
        "value": 340,
        "unitCode": "MMT",
        "referencePeriod": "dayStart"
    },
    "evapoTranspiration": {
        "type": "Property",
        "value": 40,
        "unitCode": "MIL"
    },
    "referenceEvapoTranspiration": {
        "type": "Property",
        "value": 100,
        "unitCode": "MIL"
    }
}
```