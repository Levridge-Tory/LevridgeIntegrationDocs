# InstanceConfig Settings
InstanceConfig is an object in the appsettings.json file used by the Levridge Integration Framework
to define the configuration for the Current Instance of the integration framework.

# Example
    "InstanceConfig": {
        "AzureTableConfiguration": "AzureTableConfiguration",
        "LogRequestsAndResponses": true
    }

# Definition
## InstanceConfig
The node in the appsettings.json file does not actually need to be named "InstanceConfig". 
You can use a command line parameter to specify the node name (section name) that contains
the InstanceConfig data. No matter the name, the instance config section must contain the following
attributes:
 - [AzureTableConfiguration](#AzureTableConfiguration)
 - [LogRequestsAndResponses](#LogRequestsAndResponses)

### AzureTableConfiguration
The AzureTableConfiguration attribute contains a string that specifies the configuration node (section)
that holds the Azure Table configuration used by the current instance of the Integration Framework.

This must point to a node that is a [AzureTableEntityConfiguration](./ServiceBusConfiguration.md) json object

### LogRequestsAndResponses
The LogRequestsAndResponses attribute contains a boolean that specifies whether or not to
log the requests and responses of the controllers in the current instance of the Integration 
Framework.