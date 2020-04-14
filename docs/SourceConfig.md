# SourceConfig Settings
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
 - [CDSConfigName](#CDSConfigName)
 - [SystemName](#SystemName)
 - [Direction](#Direction)

### ServiceBusConfigName
The ServiceBusConfigName attribute contains a string that specifies the configuration node (section)
that holds the service bus configuration used by the Source of the Integration Interaction.

This must point to a node that is a [ServiceBusConfig](./ServiceBusConfiguration.md) json object

### ODataConfigName
The ODataConfigName attribute contains a string that specifies the configuration node (section)
that holds the data configuration used by the Source of the Integration Interaction.

This must point to a node that is a [ODataConfig](./ODataConfig.md) json object

### CDSConfigName
The CDSConfigName attribute contains a string that specifies the configuration node (section)
that holds the CDS configuration used by the Source of the Integration Interaction.

This must point to a node that is a [CDSConfig](./CDSConfig.md) json object

### SystemName
The SystemName attribute holds a string value that represents the source system name.
It must be one of the names recognized by the [SystemName enumeration](SystemName.md).

### Direction
The direction is either Soruce or Target. This must be specified since the [SourceConfig Node](#SourceConfig) 
can have any name so the direction of the configuration may not be clear from the name.