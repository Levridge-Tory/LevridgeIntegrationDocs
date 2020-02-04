# InstanceConfig Settings
InstanceConfig is an object in the appsettings.json file used by the Levridge Integration Framework
to define the configuration for the Current Instance of the integration framework.

# Example
    "InstanceConfig": {
        "AzureTableConfiguration": "AzureTableConfiguration",
        "LogRequestsAndResponses": true,
        "EnableAppInsightsAdaptiveSampling": true
    }

# Definition
## InstanceConfig
The node in the appsettings.json file does not actually need to be named "InstanceConfig". 
You can use a command line parameter to specify the node name (section name) that contains
the InstanceConfig data. No matter the name, the instance config section must contain the following
attributes:

 - [AzureTableConfiguration](#AzureTableConfiguration)
 - [LogRequestsAndResponses](#LogRequestsAndResponses)
 - [EnableAppInsightsAdaptiveSampling](#EnableAppInsightsAdaptiveSampling)

### AzureTableConfiguration
The AzureTableConfiguration attribute contains a string that specifies the configuration node (section)
that holds the Azure Table configuration used by the current instance of the Integration Framework.

This must point to a node that is a [AzureTableEntityConfiguration](./ServiceBusConfiguration.md) json object

### LogRequestsAndResponses
The LogRequestsAndResponses attribute contains a boolean that specifies whether or not to
log the requests and responses of the controllers in the current instance of the Integration 
Framework.

### EnableAppInsightsAdaptiveSampling
The EnableAppInsightsAdaptiveSampling attribute contains a boolean that specifies whether or not to
enable application insights adaptive sampling. If this is disabled all the messages logged to 
Application Insights. This should only be used during troubleshooting and testing because the 
cost for Application Insights is billed based on volume. The default state is "true" which means
that adaptive sampling is enabled by default.

See [Sampling in Application Insights](#https://docs.microsoft.com/en-us/azure/azure-monitor/app/sampling#configuring-adaptive-sampling-for-aspnet-core-applications) 
for more information.