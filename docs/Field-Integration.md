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
      "farmID": "COP000010",
      "fieldID": "CST-000150",
      "fieldName": "Test Field Type",
      "farmableAcres" : 19.5
    }

### Authentication


### Error Codes


### Rate limit


### Message Example
    {
      "growerID": "CUS-000071",
      "farmID": "COP000010",
      "fieldID": "CST-000150",
      "fieldName": "Test Field Type",
      "farmableAcres" : 19.5
    }

### Message Schema
    1 {
    2   "definitions": {},
    3   "$schema": "http://json-schema.org/draft-07/schema#",
    4   "$id": "http://schemas.levridge.com/field.json",
    5   "type": "object",
    6   "title": "Field Schema",
    7   "properties": {
    8     "growerID": {
    9       "$id": "#/properties/growerID",
    10       "type": "string",
    11       "title": "The Growerid",
    22       "description": "Used to indicate which Customer in the Levridge system the Customer Operation belongs to.",
    12       "default": "",
    13       "examples": [
    14         "CUS-000071"
    15       ],
    16       "pattern": "^(.*)$"
    17     },
    18     "farmID": {
    19       "$id": "#/properties/farmID",
    20       "type": "string",
    21       "title": "The Farmid",
    22       "description": "Used to populate the Customer Operation to which the Field belongs",
    23       "default": "",
    24       "examples": [
    25         "COP000010"
    26       ],
    27       "pattern": "^(.*)$"
    28     },
    29     "fieldID": {
    30       "$id": "#/properties/fieldID",
    31       "type": "string",
    32       "title": "The Fieldid Schema",
    33       "description": "Used to populate the Customer Site Code",
    34       "default": "",
    35       "examples": [
    36         "CST-000150"
    37       ],
    38       "pattern": "^(.*)$"
    39     },
    40     "fieldName": {
    41       "$id": "#/properties/fieldName",
    42       "type": "string",
    43       "title": "The Fieldname Schema",
    44       "description": "The name of the field",
    45       "default": "",
    46       "examples": [
    47         "Test Field Type"
    48       ],
    49       "pattern": "^(.*)$"
    50     },
    51     "farmableAcres": {
    52       "$id": "#/properties/farmableAcres",
    53       "type": "number",
    54       "title": "The Farmableacres Schema",
    55       "default": 0.0,
    56       "examples": [
    57         19.5
    58       ]
    59     }
    60   },
    61   "required": [
    62     "farmID",
    63     "fieldID",
    64     "fieldName"
    65   ]
    66 }


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
            "RequiresSession": true
        }
    }

