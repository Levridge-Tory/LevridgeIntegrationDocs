## SystemName
SystemName is an enumerated value that is used in the 
[Source](SourceConfig.md) and [Target](TargetConfig.md) configurations 
to configure which integrations get loaded into the current 
integration framework instance.

The valid values are:
 
 - **None**: No integrations will be loaded
 - **DynamicsAX**: The integrations for Dynamics 365 Finance and Operations will be loaded as either the Source or the Target depending on which config node it appears.
 - **DynamicsCRM**: The integrations for Dynamics 365 Customer Engagement will be loaded as either the Source or the Target depending on which config node it appears.
 - **ScaleHouse**: The integrations for the Levridge Scale Application will be loaded as either the Source or the Target depending on which config node it appears.
 - **OneWeigh**: The integrations for OneWeigh will be loaded as either the Source or the Target depending on which config node it appears.
 - **AgSync**: The integrations for Agsync will be loaded as either the Source or the Target depending on which config node it appears.
 - **Recommendation**: The integrations for Recommendations will be loaded as the Source. This is not a valid value for the Target configuration.
 - **Field**: The integrations for Fields will be loaded as the Source. This is not a valid value for the Target configuration.
 - **Surety**: The integrations for Surety will be loaded as the Source. This is not a valid value for the Target configuration.
 - **Kahler**: The integrations for Kahler will be loaded as either the Source or the Target depending on which config node it appears.
