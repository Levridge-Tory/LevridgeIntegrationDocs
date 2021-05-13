# Field Integration
The Field integration is a unidirectional integration that receives messages to 
create a Levridge Customer Site using a configured Customer Site Type that represents
a customer field.

# Overview
The Field Integration API is a [Webhook](https://en.wikipedia.org/wiki/Webhook) that receives a posted message that is used
to create a new Customer Site in Levridge.

## API
    POST /api/field HTTP/1.1
    Host: [Customer Integration Framework Host]
    Content-Type: application/json

    {
      "growerID": "CUS-000071",
      "growerUuid": "5ddf9e57-b1ba-4af5-90bf-e9454e87f170",  
      "farmID": "COP000010",
      "farmUuid": "5ddf9e57-b1ba-4af5-90bf-e9454e87f171",
      "fieldID": "CST-000150",
      "fieldUuid":"5ddf9e57-b1ba-4af5-90bf-e9454e87f172",
      "fieldName": "Test Field Type",
      "fieldWkt" : "MULTIPOLYGON(((-97.027808062981 46.999026392986,-97.017851703117 46.998792242651,-97.018023364494 46.991884346149,-97.027636401605 46.991767255461,-97.027808062981 46.999026392986)))",
      "farmableAcres" : 19.5
    }

### Authentication


### Error Codes


### Rate limit


### Message Example

    {
      "growerID": "CUS-000071",
      "growerUuid": "5ddf9e57-b1ba-4af5-90bf-e9454e87f170",  
      "farmID": "COP000010",
      "farmUuid": "5ddf9e57-b1ba-4af5-90bf-e9454e87f171",
      "fieldID": "CST-000150",
      "fieldUuid":"5ddf9e57-b1ba-4af5-90bf-e9454e87f172",
      "fieldName": "Test Field Type",
      "fieldWkt" : "MULTIPOLYGON(((-97.027808062981 46.999026392986,-97.017851703117 46.998792242651,-97.018023364494 46.991884346149,-97.027636401605 46.991767255461,-97.027808062981 46.999026392986)))",
      "farmableAcres" : 19.5
    }

### Message Schema

    1 {
    2   "definitions": {},
    3   "$schema": "http://json-schema.org/draft-07/schema#",
    4   "$id": "http://example.com/root.json",
    5   "type": "object",
    6   "title": "The Root Schema",
    7   "required": [
    8     "growerID",
    9     "farmID",
    10     "fieldID",
    11     "fieldName"
    12   ],
    13   "properties": {
    14     "growerID": {
    15       "$id": "#/properties/growerID",
    16       "type": "string",
    17       "title": "The Growerid Schema",
    18       "default": "",
    19       "examples": [
    20         "CUS-000071"
    21       ],
    22       "pattern": "^(.*)$"
    23     },
    24     "growerUuid": {
    25       "$id": "#/properties/growerUuid",
    26       "type": "string",
    27       "title": "The Groweruuid Schema",
    28       "default": "",
    29       "examples": [
    30         ""
    31       ],
    32       "pattern": "^(.*)$"
    33     },
    34     "farmID": {
    35       "$id": "#/properties/farmID",
    36       "type": "string",
    37       "title": "The Farmid Schema",
    38       "default": "",
    39       "examples": [
    40         "COP000010"
    41       ],
    42       "pattern": "^(.*)$"
    43     },
    44     "farmUuid": {
    45       "$id": "#/properties/farmUuid",
    46       "type": "string",
    47       "title": "The Farmuuid Schema",
    48       "default": "",
    49       "examples": [
    50         ""
    51       ],
    52       "pattern": "^(.*)$"
    53     },
    54     "fieldID": {
    55       "$id": "#/properties/fieldID",
    56       "type": "string",
    57       "title": "The Fieldid Schema",
    58       "default": "",
    59       "examples": [
    60         "CST-000150"
    61       ],
    62       "pattern": "^(.*)$"
    63     },
    64     "fieldUuid": {
    65       "$id": "#/properties/fieldUuid",
    66       "type": "string",
    67       "title": "The Fielduuid Schema",
    68       "default": "",
    69       "examples": [
    70         "5ddf9e57-b1ba-4af5-90bf-e9454e87f172"
    71       ],
    72       "pattern": "^(.*)$"
    73     },
    74     "fieldName": {
    75       "$id": "#/properties/fieldName",
    76       "type": "string",
    77       "title": "The Fieldname Schema",
    78       "default": "",
    79       "examples": [
    80         "Test Field Type"
    81       ],
    82       "pattern": "^(.*)$"
    83     },
    84     "fieldWkt": {
    85       "$id": "#/properties/fieldWkt",
    86       "type": "string",
    87       "title": "The Fieldwkt Schema",
    88       "default": "",
    89       "examples": [
    90         "MULTIPOLYGON(((-97.027808062981 46.999026392986,-97.017851703117 46.998792242651,-97.018023364494 46.991884346149,-97.027636401605 46.991767255461,-97.027808062981 46.999026392986)))"
    91       ],
    92       "pattern": "^(.*)$"
    93     },
    94     "farmableAcres": {
    95       "$id": "#/properties/farmableAcres",
    96       "type": "number",
    97       "title": "The Farmableacres Schema",
    98       "default": 0.0,
    99       "examples": [
    100         19.5
    101       ]
    102     }
    103   }
    104 }

## Configuration
In the appsettings.json you will need to define a section named "Levridge.Integration.Host.FieldController". 
The controller looks for this section to get the Service Bus information needed to place
messages into a Topic.

You can run the Field to CRM integration in the same instance simply by pointing the SourceConfig.ServiceBusConfigName 
to "Levridge.Integration.Host.FieldController" also, or a section that defines a connection to the same topic 
the controller is sending the message to. 

For the instance that handles the integration mapping the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes should be setup as follows:

    "SourceConfig": {
        "ServiceBusConfigName": [section name with service bus topic],
        "ODataConfigName": "",
        "SystemName": "Field",
        "Direction": "Source"
    },
    "TargetConfig": {
        "ODataConfigName": [section name with CRM data configuration],
        "CDSConfigName": [section name with CDS data configuration],
        "SystemName": "DynamicsCRM",
        "Direction": "Target"
    }

In the appsettings.json you will need to add the assembly into the list of controllers. It doesn't matter
what name you assign to the assembly entry but the assembly name must be "Levridge.Integration.Host.FieldController". 
In the example below the assembly is named "FieldController". (i.e. "FieldController": "Levridge.Integration.Host.FieldController")

    "Controllers": {
        "HostController": "Levridge.Integration.Host.DefaultController",
        "FieldController": "Levridge.Integration.Host.FieldController"
    }
The "Controllers" section above will load the DefaultController and the FieldController.

    {
        "Controllers": {
            "HostController": "Levridge.Integration.Host.DefaultController",
            "FieldController": "Levridge.Integration.Host.FieldController"
        },
        "Logging": {
           "Debug": {
                "LogLevel": {
                    "Default": "Information"
                }
            },
            "Console": {
                "IncludeScopes": true,
                "LogLevel": {
                    "Default": "Information"
                }
            },
            "LogLevel": {
                "Default": "Information"
            }
        },
        "AllowedHosts": "*",
        "InstanceConfig": {
            "AzureTableConfiguration": "AzureTableConfiguration"
        },
        "SourceConfig": {
            "ServiceBusConfigName": "Levridge.Integration.Host.FieldController",
            "ODataConfigName": "CDS",
            "SystemName": "Field",
            "Direction": "Source"
        },
        "TargetConfig": {
            "ODataConfigName": "DynamicsCRM",
            "SystemName": "DynamicsCRM",
            "Direction": "Target",
            "CDSConfigName": "CDS"
        },
        "DynamicsCRM": {
            "UriString": "https://localhost",
            "ActiveDirectoryResource": "https://[Customer CRM Instance].crm.dynamics.com",
            "ActiveDirectoryTenant": "https://login.microsoftonline.com/2e14a5b1-fbf8-415b-bc7d-93e20829e510",
            "ActiveDirectoryClientAppId": "[Application ID]",
            "ActiveDirectoryClientAppSecret": "[Client Secret]",
            "ODataEntityPath": "https://[Customer CRM Instance].crm.dynamics.com/api/data/v9.0/",
            "AssemblyName": "Levridge.ODataDataSources.DynamicsCRM",
            "AssemblyFile": "Levridge.ODataDataSources.DynamicsCRM.dll",
            "ClientClassesNameSpace": "Levridge.ODataDataSources.DynamicsCRM",
            "MetadataResource": "CRMMetadata.xml"
        },
        "CDS": {
            "UriString": "https://localhost",
            "ActiveDirectoryResource": "https://[Customer CDS Instance].api.crm.dynamics.com",
            "ActiveDirectoryTenant": "https://login.microsoftonline.com/2e14a5b1-fbf8-415b-bc7d-93e20829e510",
            "ActiveDirectoryClientAppId": "[Application ID]",
            "ActiveDirectoryClientAppSecret": "[Client Secret]",
            "ODataEntityPath": "https://[Customer CDS Instance].api.crm.dynamics.com/api/data/v9.0/",
            "AssemblyName": "Levridge.ODataDataSources.CDS",
            "ClientClassesNameSpace": "Levridge.ODataDataSources.CDS",
            "MetadataResource": "CDSMetadata.xml"
        },
        "AzureTableConfiguration": {
            "ConnectionString": "DefaultEndpointsProtocol=https;AccountName=levridgegeneralstorage;AccountKey=MFkzIfLUU1KyCMxfZVPk7HelhWlC0TZyBnFDMEty4y3D4YnqgA4RHSHu8es+R91C/MmDNjtuKJ1x8yDMJ4vLGA==;EndpointSuffix=core.windows.net",
            "Table": "FinOpsAndCRM"
        },
        "Levridge.Integration.Host.FieldController": { // used by Webhook
            "ConnectionString": "Endpoint=sb://[Customer Service Bus Instance].servicebus.windows.net/;SharedAccessKeyName=RootManageSharedAccessKey;SharedAccessKey=[Customer Access Key]",
            "TopicName": "[Customer Topic Name]",
            "SubscriptionName": "[Customer Subscription Name]",
            "RequiresSession": true,
            "CustomerSiteTypeCode": "[CustomerSite TypeCode from FinOps]",
            "IdOption": "FieldId"
        }
    }

