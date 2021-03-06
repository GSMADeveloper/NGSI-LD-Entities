# Weather Forecast
This entity contains a harmonised description of a Weather Forecast. This entity is primarily associated with the vertical segments of the environment and agriculture but is applicable to many different applications.

| Attribute Name | Attribute Type | Description | Constraint |
|:--- |:--- |:--- |:---:|
| id | @id | Provides a unique identifier for an instance of the entity either in the form of a URI (i.e. either a publicly accessible URL or a URN). | Mandatory |
| type | @type | Defines the type of the entity. | Mandatory |
| createdAt | TemporalProperty | Indicates the date/ time that the instance of the entity was created in ISO 8601 format. The value of this will be set by the server when the entity was created. | Mandatory |
| modifiedAt | TemporalProperty | Indicates the date/ time when the entity was last modified in ISO 8601 format. The value of this will be set by the server when the entity was modified, if the entity has not been modified it may have a null value. | Optional |
| source | Property | Specifies the URL to the source of this data (either organisation or where relevant more specific source) | Recommended |
| dataProvider | Property | Specifies the URL to information about the provider of this information | Recommended |
| entityVersion | Property | The entity specification version as a number. A version number of 2.0 or later denotes the entity is represented using NGSI-LD | Recommended |
| POIs | Relationship | A reference to associated Points of Interest (e.g. monitoring station) that this forecast is related to. | Recommended |
| location | GeoProperty | The geo location (point/ polygon) for this forecast. | Mandatory |
| retrievedAt | DateTime | Indicates the date/time the forecast was retrieved from the associated meteorological agency. | Mandatory |
| issuedAt | DateTime | Indicates the date/time the forecast was issued by the associated meteorological agency. | Recommended |
| weatherType | Property | The weather type. A choice from an enumerated list. One of: **notAvailable, clearNight, sunnyDay, partlyCloudy, mist, fog, cloudy, overcast, lightRainShower, drizzle, lightRain, heavy RainShower, heavyRain, sleetShower, sleet, hailShower, hail, lightSnow Shower, lightSnow, heavySnowShower,heavySnow, thunderShower, thunder.** | Recommended |
| visibility | Property | Defines the forecast visibility nominally in metres or in an alternative measurement according to specified unitCode | Recommended |
| name | Property | The name of the weather forecast location. | Mandatory |
| validFrom | DateTime | The date and time the forecast is valid from. | Recommended |
| validThrough | DateTime | The date and time the forecast is valid to. | Recommended |
| dayMinimum | Property | Defines the minimum forecast values for defined attributes.

Supports the inclusion of the nested attribute values, each of which will be a number. The units of the respective values will match the respective main attributes for temperature/ relative humidity.

**temperature, feelsLikeTemperature, relativeHumidity**

**temperature** -- The forecasted minimum temperature for the period in degrees Celsius.

**feelsLikeTemperature** – The forecasted feels like temperature for the period in degrees Celsius.

**relativeHumidity** -- The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100% | Optional |
| dayMaximum | Property | Defines the maximum forecast values for defined attributes.

Supports the inclusion of the nested attribute values, each of which will be a number. The units of the respective values will match the respective main attributes for temperature/ relative humidity.

**temperature, feelsLikeTemperature, relativeHumidity**

**temperature** -- The forecasted minimum temperature for the period in degrees Celsius.

**feelsLikeTemperature** – The forecasted feels like temperature for the period in degrees Celsius.

**relativeHumidity** -- The relative humidity expressed a number between 0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100% | Optional |
| address | Property | The weather forecast location encoded as a Schema.org PostalAddress. https://schema.org/PostalAddress | Recommended |
| temperature | Property | The temperature expressed in degrees Celsius. | Recommended |
| windDirection | Property | The wind direction expressed in degrees compared to geographic North (measured clockwise). | Optional |
| windSpeed | Property | The forecasted wind speed in meters per second. | Optional |
| uVIndexMax | Property | The maximum UV index for the period, based on the World Health Organization's UV Index measure. | Optional |
| relativeHumidity | Property | The relative humidity expressed a number between\n\n0 ≤ RelativeHumidity ≤ 1 representing the range 0% to 100% | Optional |
| precipitationProbability | Property | The probability of precipitation, expressed as a number between\n\n0 ≤ precipitationProbability ≤ 1 representing the range 0% to 100% | Optional |
| <em>dateRetrieved</em> | <em>DateTime</em> | <em>Indicates the date/time the forecast was retrieved from the associated meteorological agency.<br/><br/>Note this field was defined for use with NGSIv2 and is now deprecated. For new entities and applications replace with **retrievedAt**</em> | <em>Deprecated</em> |
| <em>dateIssued</em> | <em>DateTime</em> | <em>Indicates the date/time the forecast was issued by the associated meteorological agency.<br/><br/>Note this field was defined for use with NGSIv2 and is now deprecated. For new entities and applications replace with **issuedAt**</em> | <em>Deprecated</em> |

## NGSI-LD Context Definition
The following NGSI-LD context definition applies to the **Weather Forecast** entity

[Download context definition.](../examples/Weather-Forecast-context.jsonld)

```JavaScript
{
    "@context": {
        "source": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/source",
        "dataProvider": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dataprovider",
        "entityVersion": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/entityversion",
        "POIs": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/pois",
        "location": "http://uri.etsi.org/ngsi-ld/location",
        "retrievedAt": {
            "@type": "DateTime",
            "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/retrievedat"
        },
        "issuedAt": {
            "@type": "DateTime",
            "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/issuedat"
        },
        "weatherType": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/weathertype",
        "visibility": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/visibility",
        "name": "https://schema.org/name",
        "validFrom": {
            "@type": "DateTime",
            "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/validfrom"
        },
        "validThrough": {
            "@type": "DateTime",
            "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/validthrough"
        },
        "dayMinimum": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dayminimum",
        "dayMaximum": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/daymaximum",
        "address": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/address",
        "temperature": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/temperature",
        "windDirection": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/winddirection",
        "windSpeed": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/windspeed",
        "uVIndexMax": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/uvindexmax",
        "relativeHumidity": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/relativehumidity",
        "precipitationProbability": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/precipitationprobability",
        "dateRetrieved": {
            "@type": "DateTime",
            "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dateretrieved"
        },
        "dateIssued": {
            "@type": "DateTime",
            "@id": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dateissued"
        }
    }
}
```
## Example of Weather Forecast Entity
The following is an example instance of the **Weather Forecast** entity

[Download example entity definition.](../examples/Weather-Forecast.jsonld)

```JavaScript
{
    "@context": [
        "https://forge.etsi.org/gitlab/NGSI-LD/NGSI-LD/raw/master/coreContext/ngsi-ld-core-context.json",
        "https://raw.githubusercontent.com/GSMADeveloper/NGSI-LD-Entities/master/examples/Weather-Forecast-context.jsonld"
    ],
    "id": "urn:ngsi-ld:WeatherForecast:7453c443-290d-44ef-a60f-d4c087010c88",
    "type": "WeatherForecast",
    "createdAt": "2017-01-01T01:20:00Z",
    "modifiedAt": "2017-05-04T12:30:00Z",
    "source": "https://source.example.com",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "POIs": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:POI:cdfd9cb8-ae2b-47cb-a43a-b9767ffd5c84",
            "urn:ngsi-ld:POI:42dcd5ea-46db-11e8-bea0-772aba733f93",
            "urn:ngsi-ld:POI:4912d78e-46db-11e8-8572-ab2b8e55590b"
        ]
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
    "retrievedAt": {
        "type": "Property",
        "value": "2017-05-04T10:18:16Z"
    },
    "issuedAt": {
        "type": "Property",
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
    "name": {
        "type": "Property",
        "value": "London City"
    },
    "validFrom": {
        "type": "Property",
        "value": "2016-08-10T10:18:16Z"
    },
    "validThrough": {
        "type": "Property",
        "value": "2016-08-29T10:18:16Z"
    },
    "dayMinimum": {
        "type": "Property",
        "value": {
            "temperature": {
                "value": 30,
                "unitCode": "CEL"
            },
            "feelsLikeTemperature": {
                "value": 32,
                "unitCode": "CEL"
            },
            "relativeHumidity": {
                "value": 0.22,
                "unitCode": "C62"
            }
        }
    },
    "dayMaximum": {
        "type": "Property",
        "value": {
            "temperature": {
                "value": 33,
                "unitCode": "CEL"
            },
            "feelsLikeTemperature": {
                "value": 38,
                "unitCode": "CEL"
            },
            "relativeHumidity": {
                "value": 0.52,
                "unitCode": "C62"
            }
        }
    },
    "address": {
        "type": "Property",
        "value": {
            "@type": "https://schema.org/PostalAddress",
            "addressLocality": "London",
            "postalCode": "EC4N 8AF",
            "streetAddress": "25 Walbrook"
        }
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
    "uVIndexMax": {
        "type": "Property",
        "value": 5,
        "unitCode": "C62"
    },
    "relativeHumidity": {
        "type": "Property",
        "value": 0.1,
        "unitCode": "C62"
    },
    "precipitationProbability": {
        "type": "Property",
        "value": 0.05,
        "unitCode": "C62"
    }
}
```
