# Deploying Custom Field Maps
This document explains how to deploy a custom field mapping assembly. See [Integrating Custom Fields](./IntegratingCustomFields.md) for instructions
on how to create a custom field mapping assembly.


# Overview
If you have developed custom field mapping assembly you will have to deploy it to a Levridge
Integration Framework instance.

You will need to deploy the custom mapping assembly library and any custom proxy
libraries you may have built.

## Deployment
It is important to deploy only the custom assemblies and not any referenced assemblies that 
are shared with the Levridge Integration Framework. The referenced assemblies will already
be deployed with the Levridge Integration Framework.

To avoid deploying the shared referenced assemblies, be sure to follow the instructions in
the section titled [Update the references to be excluded from deployment](./IntegratingCustomFields.md#update-the-references-to-be-excluded-from-deployment).

You can use visual studio to [deploy to a local folder](https://docs.microsoft.com/en-us/visualstudio/deployment/quickstart-deploy-to-local-folder?view=vs-2019#deploy-to-a-local-folder)
or use Azure DevOps to obtain a zipped folder or your custom assemblies.

You will need to copy the custom assemblies into the same folder as the Levridge Integration
Framework.

## Configuration
You will need to add a [CustomMappingAssemblies](./CustomMappingConfig.md) node to the appsettings.json file.

