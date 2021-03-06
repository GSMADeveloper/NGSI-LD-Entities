# UAV TMS
This entity contains a harmonised description of a specific Unmanned Aerial Vehicle (UAV) Traffic Management Software Application that is designed to listen to and monitor the information transmitted by UAV’s, typically this software application would be operated at a ground station. This entity is primarily associated with UAV command and control applications.

| Attribute Name | Attribute Type | Description | Constraint |
|:--- |:--- |:--- |:---:|
| id | @id | Provides a unique identifier for an instance of the entity either in the form of a URI (i.e. either a publicly accessible URL or a URN). | Mandatory |
| type | @type | Defines the type of the entity. | Mandatory |
| createdAt | TemporalProperty | Indicates the date/ time that the instance of the entity was created in ISO 8601 format. The value of this will be set by the server when the entity was created. | Mandatory |
| modifiedAt | TemporalProperty | Indicates the date/ time when the entity was last modified in ISO 8601 format. The value of this will be set by the server when the entity was modified, if the entity has not been modified it may have a null value. | Optional |
| source | Property | Specifies the URL to the source of this data (either organisation or where relevant more specific source) | Recommended |
| dataProvider | Property | Specifies the URL to information about the provider of this information | Recommended |
| entityVersion | Property | The entity specification version as a number. A version number of 2.0 or later denotes the entity is represented using NGSI-LD | Recommended |
| name | Property | The name of this software application. | Recommended |
| softwareApplication | Property | Details about the software application using the Schema.org definition https://schema.org/SoftwareApplication | Mandatory |
| operationalInstance | Property | URL linking to an operational instance (assumed to be web based) for the UAV Traffic Management Software. | Mandatory |
| owner | Property | A list detailing the owner or owners of the TMS software.

Refers to one or more Schema.org person or organization.

https://schema.org/Person

https://schema.org/Organization | Recommended |
| operator | Property | A list detailing the operator or operators of the TMS software.

Refers to one or more Schema.org person or organization.

https://schema.org/Person

https://schema.org/Organization | Recommended |

## NGSI-LD Context Definition
The following NGSI-LD context definition applies to the **UAV TMS** entity

[Download context definition.](../examples/UAV-TMS-context.jsonld)

```JavaScript
{
    "@context": {
        "source": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/source",
        "dataProvider": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/dataprovider",
        "entityVersion": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/entityversion",
        "name": "https://schema.org/name",
        "softwareApplication": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/softwareapplication",
        "operationalInstance": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/operationalinstance",
        "owner": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/owner",
        "operator": "https://www.gsma.com/iot/iot-big-data/ngsi-ld/operator"
    }
}
```
## Example of UAV TMS Entity
The following is an example instance of the **UAV TMS** entity

[Download example entity definition.](../examples/UAV-TMS.jsonld)

```JavaScript
{
    "@context": [
        "https://forge.etsi.org/gitlab/NGSI-LD/NGSI-LD/raw/master/coreContext/ngsi-ld-core-context.json",
        "https://raw.githubusercontent.com/GSMADeveloper/NGSI-LD-Entities/master/examples/UAV-TMS-context.jsonld"
    ],
    "id": "urn:ngsi-ld:UAVTMS:e0ad01b2-592a-11e8-bf93-cf2039a6c0cf",
    "type": "UAVTMS",
    "createdAt": "2017-01-01T01:20:00Z",
    "modifiedAt": "2017-05-04T12:30:00Z",
    "source": "https://source.example.com",
    "dataProvider": "https://provider.example.com",
    "entityVersion": 2.0,
    "name": {
        "type": "Property",
        "value": "PowerTMS"
    },
    "softwareApplication": {
        "type": "Property",
        "value": {
            "@type": "https://schema.org/SoftwareApplication",
            "operatingSystem": "Linux",
            "softwareVersion": "8.3",
            "applicationCategory": "Guidance"
        }
    },
    "operationalInstance": {
        "type": "Property",
        "value": {
            "@value": "http://example.com/uavtms",
            "@type": "https://schema.org/url"
        }
    },
    "owner": {
        "type": "Property",
        "value": [
            "urn:ngsi-ld:Person:bd710472-592b-11e8-852c-6fd149eae28a",
            "urn:ngsi-ld:Organization:c5d75a1c-592b-11e8-8a09-3bd13644426b"
        ]
    },
    "operator": {
        "type": "Property",
        "value": [
            "urn:ngsi-ld:Person:bd710472-592b-11e8-852c-6fd149eae28a",
            "urn:ngsi-ld:Person:cbec3f1c-592b-11e8-943c-57802974f852"
        ]
    }
}
```
