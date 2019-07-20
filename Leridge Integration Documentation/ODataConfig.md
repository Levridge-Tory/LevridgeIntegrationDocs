# Introduction
SourceConfig is an object in the appsettings.json file used by the Levridge Integration Framework
to define the configuration for the Source of an integration interaction.

# Example
    "SourceConfig": {
        "ServiceBusConfigName": "Levridge.Integration.Host.SuretyController",
        "ODataConfigName": "DynamicsCRM",
        "SystemName": "Surety",
        "Direction": "Source"
    }

# Definition
## SourceConfig
The node in the appsettings.json file does not actually need to be named "SourceConfig". 
You can use a command line parameter to specify the node name (section name) that contains
the SourceConfig data. No matter the name, the source config section must contain the following
attributes:
 - [ServiceBusConfigName](#ServiceBusConfigName)
 - [ODataConfigName](#ODataConfigName)
 - [SystemName](#SystemName)
 - [Direction](#Direction)

### ServiceBusConfigName
The ServiceBusConfigName attribute contains a string that specifies the configuration node (section)
that holds the service bus configuration used by the Source of the Integration Interaction.

This must point to a node that is a [ServiceBusConfig](ServiceBusConfig.md) json object


### ODataConfigName

### SystemName

### Direction