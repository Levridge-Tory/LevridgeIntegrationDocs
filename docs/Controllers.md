# Controllers Settings
Controllers section is a json object in the appsettings.json file used by the Levridge Integration Framework
to define which controllers to load for the current Levridge Integration Framework instance.

# Example

    "Controllers": {
        "HostController": "Levridge.Integration.Host.DefaultController",
        "AgSyncConroller": "Levridge.Integration.Host.AgSyncController"
    },


# Definition
## Controllers
The controllers json object is comma delimited list of json objects that define which controllers to load
for the current Levridge Integration Framework instance. Each json object contains a name and an assembly name.
The name is not used by the system, but is used to provide a human friendly name for the assembly 
referenced with it.  

In the example above, the Controllers object informs the Levridge Integration Framework to load
two assemblies:
 - "Levridge.Integration.Host.DefaultController"
 - "Levridge.Integration.Host.AgSyncController"

# See Also
[Controller Security](./ControllerSecurity.md)