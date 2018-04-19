# Agri Greenhouse
This entity contains a harmonised description of the conditions recorded within a generic greenhouse, a type of AgriParcel. This entity is primarily associated with the agricultural vertical and related IoT applications.

| Attribute Name | Attribute Type | Description | Constraint |
|:--- |:--- |:--- |:---:|
| id | @id | Provides a unique identifier for an instance of the entity either in the form of a URI (i.e. either a publicly accessible URL or a URN). | Mandatory |
| type | @type | Defines the type of the entity. | Mandatory |
| createdAt | DateTime | Indicates the date/ time that the instance of the entity was created in ISO 8601 format. The value of this will be set by the server when the entity was created. | Mandatory |
| modifiedAt | DateTime | Indicates the date/ time when the entity was last modified in ISO 8601 format. The value of this will be set by the server when the entity was modified, if the entity has not been modified it may have a null value. | Optional |
| source | Property | Specifies the URL to the source of this data (either organisation or where relevant more specific source) | Recommended |
| dataProvider | Property | Specifies the URL to information about the provider of this information | Recommended |
| entityVersion | Property | The entity specification version as a number. A version number of 2.0 or later denotes the entity is represented using NGSI-LD | Recommended |
| agriParcelParent | Relationship | Reference to the AgriParcel entity to which this entity relates. | Mandatory |
| agriParcelChildren | Relationship | Related sub AgriParcel records to which this entity relates. | Optional |
| weatherObserved | Relationship | Reference to the weather observation record current for this entity. | Mandatory |
| waterQualityObserved | Relationship | Reference to one or more water quality observation records current for this entity. | Optional |
| relativeHumidity | Property | The inside relative humidity expressed as a number between 0 and 1 representing the range 0% to 100 (%).<br/><br/>0 ≤ relativeHumidity ≤ 1 | Recommended |
| leafTemperature | Property | The average greenhouse air temperature nominally in degrees centigrade. | Recommended |
| co2 | Property | The measured interior C02 concentration nominally in mg/L. | Optional |
| dailyLight | Property | Daily Accumulated light measured in kW per square metre | Optional |
| drainFlow | Property | The observed drain flow rate in litres per second | Optional |

## NGSI-LD Context Definition
The following NGSI-LD context definition applies to the **Agri Greenhouse** entity

[Download context definition.](../examples/Agri-Greenhouse-context.jsonld)

```JavaScript
{
    "id": "@id",
    "type": "@type",
    "DateTime": "http://uri.etsi.org/ngsi-ld/DateTime",
    "createdAt": {
        "@id": "http://uri.etsi.org/ngsi-ld/createdAt",
        "@type": "DateTime"
    },
    "modifiedAt": {
        "@id": "http://uri.etsi.org/ngsi-ld/modifiedAt",
        "@type": "DateTime"
    },
    "Property": "http://etsi.org/nsgi-ld/Property",
    "Relationship": "http://uri.etsi.org/ngsi-ld/Relationship"
}
```
## Example of Agri Greenhouse Entity
The following is an example instance of the **Agri Greenhouse** entity

[Download example entity definition.](../examples/Agri-Greenhouse.jsonld)

```JavaScript
{
    "@context": [
        "https://example.com/contexts/coreContext.jsonld",
        "https://example.com/contexts/agri-greenhouse.jsonld"
    ],
    "id": "urn:ngsi-ld:AgriGreenhouse:df72dc57-1eb9-42a3-88a9-8647ecc954b4",
    "type": "AgriGreenhouse",
    "createdAt": "2017-01-01T01:20:00Z",
    "modifiedAt": "2017-05-04T12:30:00Z",
    "source": "https://source.example.com",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "agriParcelParent": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:AgriParcel:c8b475e5-84a8-4346-ad79-cde1d2a4028b"
    },
    "agriParcelChildren": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:AgriParcel:8c3a525d-b42e-4048-bcdd-a119d8ddb0a5",
            "urn:ngsi-ld:AgriParcel:178d74c1-e6fe-4042-b955-2c164fc90b83"
        ]
    },
    "weatherObserved": {
        "type": "Relationship",
        "object": "urn:ngsi-ld:WeatherObserved:c720cec5-ac6f-40b7-8e89-becb75702d0d"
    },
    "waterQualityObserved": {
        "type": "Relationship",
        "object": [
            "urn:ngsi-ld:WaterQualityObserved:49f86e0b-bb90-4751-a1c3-d5a891920807",
            "urn:ngsi-ld:WaterQualityObserved:853bf420-43fc-11e8-942f-6b7615517118"
        ]
    },
    "relativeHumidity": {
        "type": "Property",
        "value": 0.4,
        "unitCode": "C62",
        "observedAt": "2016-08-22T19:20Z"
    },
    "leafTemperature": {
        "type": "Property",
        "value": 22,
        "unitCode": "CEL",
        "observedAt": "2016-08-22T19:20Z"
    },
    "co2": {
        "type": "Property",
        "value": 28,
        "unitCode": "M1",
        "observedAt": "2016-08-22T19:20Z"
    },
    "dailyLight": {
        "type": "Property",
        "value": 24,
        "unitCode": "N78",
        "observedAt": "2016-08-22T19:20Z"
    },
    "drainFlow": {
        "type": "Property",
        "value": 33,
        "maxValue": 50,
        "minValue": 25,
        "unitCode": "G51",
        "unitText": "Litre per second",
        "observedAt": "2016-08-22T19:20Z"
    }
}
```