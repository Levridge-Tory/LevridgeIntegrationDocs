# appsettings.json 
The appsettings.json is a configuration file that is used in standard 
[Microsoft Configuration for ASP.NET Core](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/configuration/?tabs=basicconfiguration&view=aspnetcore-3.1)
to provide application settings.

This document explains the various json objects used in the appsettings.json file.

# Overview

## Controllers
The controllers section provides a list of json objects that define which controllers to load
for the current Levridge Integration Framework instance.

See [Controllers Settings](./Controllers.md)

## Logging
The Levridge Integration Framework utilizes the standard [ASP.NET Core logging](https://docs.microsoft.com/en-us/aspnet/core/fundamentals/logging/?view=aspnetcore-3.1) capabilities.
The Logging section defines the logging settings for the various logging providers being used.

See [Logging Settings](./Logging.md)

## InstanceConfig
The InstanceConfig section is a json object used by the Levridge Integration Framework
to define the configuration for the Current Instance of the integration framework.

See [InstanceConfig Settings](./InstanceConfig.md)

## SourceConfig
The SourceConfig section is a json object used by the Levridge Integration Framework
to define the configuration for the Source of an integration interaction.

See [SourceConfig Settings](./SourceConfig.md)

## TargetConfig
The TargetConfig section is a json object used by the Levridge Integration Framework
to define the configuration for the Target of an integration interaction.

See [TargetConfig Settings](./TargetConfig.md)

