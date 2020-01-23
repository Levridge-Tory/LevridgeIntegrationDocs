<!-- -->
# Introduction
In many implementations a client will have specific needs that require custom fields to be added to
existing entities. This document shows how to create a custom field extension to have those custom
fields integrated when the entity is being integrated.

# Overview
In order to integrate custom fields you will need to create a Visual Studio solution with three
projects:

* Custom Source Proxy Project

  Contains the proxy for the source datasource with the custom fields in the entities
* Custom Destination Proxy Project

  Contains the proxy for the desitination datasource with the custom fields in the entities
* Custom Mapping Project

  Contains the code need to map the integration for the custom fields between the source and 
destination entities

# Tutorial
## Create the Solution
The first step is to create a Visual Studio solution for the custom mapping.
In Visual Studio, create a new C# Class Library (.NET Core).
![Class Library](./assets/images/IntegratingCustomFields/ClassLibraryProject.jpg "Class Library Project Type")

You may want to give the solution a different name than the project. In our example, the customer is Comstock
so we will name the solution "ComstockCustomMapping" and the project Levridge.Integration.IntegrationService.Mapping.Comstock.
We recommend you use this naming convention for your custom mapping project: Levridge.Integration.IntegrationService.Mapping.[clientname].
![Project Configuration](./assets/images/IntegratingCustomFields/ConfigureNewProject.jpg "New Project Configuration")

## Create the Source Proxy Project

## Create the Destination Proxy Project

## Add References to the Custom Mapping Project
You will need to add the following Nuget references to your custom mapping project:

* Levridge.EntityFramework
* Levridge.Integration.IntegrationService.Abstractions
* Levridge.Integration.IntegrationService.Mapping
* Microsoft.Extensions.DependencyInjection

## Add Destination Datasource References to Custom Mapping Project
You will need to reference the destination data source project in order to have acess to any 
Field types and other types used during mapping. If your destination is CRM you would include
the following references.

* Levridge.ODataDataSources.CRMODataDataSource

### Update the references to be excluded from deployment
These references will be needed for the build process, but we will want to use the libraries
provided by the standard deployment and not deploy our own copy of the libraries with the custom
mapping assemblies. To accomplish this, we let the msbuild system know to exclude these
libraries from the runtime deployment by adding `<ExcludeAssets>runtime</ExcludeAssets>` to the 
`<PackageReference>` node for each package. You should have an `<ItemGroup>` node that looks somthing like
this.

```
  <ItemGroup>
    <PackageReference Include="Levridge.EntityFramework" Version="2.0.10">
      <ExcludeAssets>runtime</ExcludeAssets>
    </PackageReference>
    <PackageReference Include="Levridge.Integration.IntegrationService.Abstractions" Version="1.0.0">
      <ExcludeAssets>runtime</ExcludeAssets>
    </PackageReference>
    <PackageReference Include="Levridge.Integration.IntegrationService.Mapping" Version="1.0.0">
      <ExcludeAssets>runtime</ExcludeAssets>
    </PackageReference>
    <PackageReference Include="Levridge.ODataDataSources.CRMODataDataSource" Version="2.1.15">
      <ExcludeAssets>runtime</ExcludeAssets>
    </PackageReference>
    <PackageReference Include="Microsoft.Extensions.DependencyInjection" Version="3.0.2">
      <ExcludeAssets>runtime</ExcludeAssets>
    </PackageReference>
  </ItemGroup>
```

## Add a reference to the two datasource proxy projects

