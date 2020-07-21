# Custom Mapping Assemblies Config Settings
The CustomMappingAssemblies configuration node is used to define any 
custom mapping assemblies to be loaded by the integration framework and
the class method to call to register the custom mapping from the assembly.

This node is a list (not an array) of named CustomPluginAssemblyConfig
json objects.

# Example
    "CustomMappingAssemblies": {
        "CustomFieldsAssembly": {
            "AssemblyName": "Levridge.Integration.IntegrationService.Mapping.CustomFields",
            "Namespace": "Levridge.Integration.IntegrationService.Mapping.CustomFields",
            "ClassName": "CustomFieldsEntityMapBuilderExtensions",
            "MethodName": "AddCustomFields"
        }
    },

# Definition
The CustomMappingAssemblies node above has a single CustomPluginAssemblyConfig object
named "CustomeFieldAssembly".

## Name
**Required**

**Default:**
No default value.

This is the name of the custom mapping assembly configuration. 
Each configuration in the list must have a unique name.
Because you can have multiple classes and or multiple methods we do 
not use the AssemblyName as the configuration name. 

## AssemblyName
**Required**

**Default:**
No default value.

This is the actual name of the assembly, not the file name. In the current
version the file name is assumed to be the "[AssemblyName].dll". Do not add
the file extension or a file path to this value.

## NameSpace
**Required**

**Default:**
No default value.

This property must contain the namespace that contains the class. This value will
be added to the class name to obtain the class type. 

## ClassName
**Required**

**Default:**
No default value.

This property is the name of the class that contains the method used to register
the custom mapping. Do not include the namespace. The namespace will be added to
the class name to obtain the type.

## MethodName
**Required**

**Default:**
No default value.

This property is the name of the method that will be called on the class 
that is used to register the custom mapping. Do not include the class name here.
