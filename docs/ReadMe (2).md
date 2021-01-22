# Introduction
The Levridge integration framework provides integration between Dynamics365 Finance and Operations
and Dynamics 365 Customer Engagement and 3rd party applications.

This document provides and overview of the integration framework and links to the document
that exists for the framework.

# Overview
The Levridge Integration Framework is an entity syncronization framework. 
It provides a means to synchronize data at an entity level between multiple data sources.

All integrations that use the framework follow the same pattern:
  1. A data source has an integration event
  2. The data source responds to the integration event by sending one or more entities to the service bus.
  3. The service bus publishes the message(s) to each subscription
  4. An instance of the integration framework receives the message(s) from a subscription
  5. The integration framework transforms the message it if needed
  6. The integration framework sends the message to the target data source

![General Entity Integartion Pattern.](./assets/images/GeneralSynchronizationIntegrations.jpg "General Entity Integartion Pattern")



# Integrations

Currently we support the following integrations:
 - [D365 F&O to D365 CRM](#D365-F&O-to-D365-CRM)
 - [D365 CRM to D365 F&O](#D365-CRM-to-D365-F&O)
 - [Kahler](#Kahler)
 - [Agsync](#Agsync)
 - [oneWeigh](#oneWeigh)
 - [Field Reveal](#Field-Reveal)
 - [Surety](#Surety)
 - [Levridge Scale House](#Levridge-Scale-House)

## D365 F&O to D365 CRM

### Setup
To integrate from D365 F&O to D365 CRM you will need to:
 - [configure Levridge Entity Events](./event_framework.md)
 - [Create an application ID](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) for the integration framework to authenticate to D365 CRM
 - [Create an application user in D365 CRM](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/use-multi-tenant-server-server-authentication#create-an-application-user--associated-with-the-registered-application--in-) and assign the proper role(s)
 - Create an Azure Service bus topic
 - Create a subscription on the topic above

### Configuration
In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

    "SourceConfig": {
        "ServiceBusConfigName": [section name with service bus topic],
        "ODataConfigName": [section name with F&O data configuration],
        "SystemName": "DynamicsAX",
        "Direction": "Source"
    },
    "TargetConfig": {
        "ODataConfigName": [section name with CRM data configuration],
        "CDSConfigName": [section name with CDS data configuration],
        "SystemName": "DynamicsCRM",
        "Direction": "Target"
    }

## D365 CRM to D365 F&O
### Setup
To integrate from D365 CRM to D365 F&O you will need to:
 - Configure Azure Service Bus Endpoint in CRM
 - Configure Azure Service Bus plugin on the appropriate entities
 - [Create an application ID](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) for the integration framework to authenticate to D365 F&O
 - [Create an Azure Active Directory Application in D365 F&O](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/data-entities/services-home-page#authentication)
 - Create an Azure Service bus topic
 - Create a subscription on the topic above

### Configuration
In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

    "SourceConfig": {
        "ServiceBusConfigName": [section name with service bus topic],
        "ODataConfigName": [section name with CRM data configuration],
        "SystemName": "DynamicsCRM",
        "Direction": "Source"
    },
    "TargetConfig": {
        "ODataConfigName": [section name with F&O data configuration],
        "CDSConfigName": [section name with CDS data configuration],
        "SystemName": "DynamicsAX",
        "Direction": "Target"
    }

## Kahler
The Kahler integration is a bidirectional integration that consists of a Topic for
Dispensing Work Orders that go from D365 F&O to Kahler and Dispensing Work Records that go from 
Kahler to D365 F&O. This means there are two instances of the integration running
to handle the entire integration.

One aspect of Kahler that is different from other integrations is the D365 F&O to Kahler
instance must run on premise because the Kahler system runs behind the firewall. This
should be deployed as a service.

Another aspect that is different is that each location should only get the messages from the 
topic that apply to that location. This is done with a filter on the service bus topic subscription.
In order for the filter to work the Levridge Entity Event must be configured to expose
the branch property on the message.

### Setup
To integrate to and from Kahler and D365 F&O you will need to:
 - [Configure Levridge Entity Events]("./Configuring%20Levridge%20Entity%20Events.md")
   - You will need to be sure to provide properties on the event to allow filtering by Branch
 - [Create an application ID](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) for the integration framework to authenticate to D365 F&O
 - [Create an Azure Active Directory Application in D365 F&O](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/data-entities/services-home-page#authentication)
 - Create an Azure Service bus topic for Dispensing Work Orders (D365 F&O to Kahler)
 - Create an Azure Service bus topic for Dispensing Work Records (Kahler to D365 F&O)
 - Create a subscription on the Dispensing Work Order topic for each Branch that has a Kahler mixer
 - Create a filter on the subscription for each Branch
 - Create a subscription on the Dispensing Work Record topic for integration back to F&O
 - [Deploy the Levridge Integration Framework as a service](./Deploy-Integration-As-A-Service.md) at each Branch that has a Kahler mixer

### Configuration for Kahler on Premise
This configuration will need to be on premise with the Kahler mixer.

In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

    "Controllers": {
        "HostController": "Levridge.Integration.Host.DefaultController",
        "KahlerConroller": "Levridge.Integration.Host.KahlerController"
    },
    "SourceConfig": {
        "ServiceBusConfigName": "Dispensing Work Order", //[section name with Dispensing Work Order service bus topic]
        "ODataConfigName": "DynamicsAX", //[section name with F&O data configuration]
        "SystemName": "DynamicsAX",
        "Direction": "Source"
    },
    "TargetConfig": {
        "ODataConfigName": "Kahler End Point", //[section name with Kahler data configuration],
        "CDSConfigName": [section name with CDS data configuration],
        "SystemName": "Kahler",
        "Direction": "Target"
    },
    "DynamicsAX": {
        "UriString": [URL to D365 F&O],
        "ActiveDirectoryResource": [URL to D365 F&O],
        "ActiveDirectoryTenant": "https://login.microsoftonline.com/[Customer_Tenant_ID]",
        "ActiveDirectoryClientAppId": [Application ID used to register the application in AD],
        "ActiveDirectoryClientAppSecret": [Client Secret genrated for the Application ID in AD],
        "ODataEntityPath": "[URL to D365 F&O]/data/"
    },
    "Kahler End Point": {
        "UriString": [URL to Local Kahler]
    },
    "Dispensing Work Order": {
        "ConnectionString": [connection string to Dispensing Work Order Topic],
        "TopicName": [Dispensing Work Order Topic Name],
        "SubscriptionName": [Subscription Name for the Branch],
        "RequiresSession": true
    },
    "Levridge.Integration.Host.KahlerController": {
        "ConnectionString": [connection string to Dispensing Work Record Topic],
        "TopicName": [Dispensing Work Record Topic Name],
        "RequiresSession": true
    }


#### Controllers
This section contains a list of controllers that will be loaded by the current instance. In addition to the default 
controller that we alwasy want to load, we want the system to load the Kahler controller. The names (on the left) are not
significant and are used only for debugging. The values (on the right) are significant. It must be the name of the assembly
that should be loaded for the controller.

#### [SourceConfig](./SourceConfig.md)
The source config will represent the data being send from D365 F&O. Currently, the Dispensing Work Order is the only entity
sent from F&O. In the future the topic may also include master data that is sent to Kahler.

The ODataConfigName is not currently being used but is a required value. So point it to the section that contains the connection
information to D365 F&O.

#### [TargetConfig](./TargetConfig.md)
The target config will represent the data endpoint for the local Kahler mixer. The "ODataConfigName" should point to a section
that contains the Kahler REST endpoint.

#### Levridge.Integration.Host.KahlerController
This section is used by the Kahler controller to be able to send messages to the proper topic to be handled by the integration
framework and written to D365 F&O

### Configuration for Kahler in Azure
This instance can be a single instance runing in the cloud.

In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

    "SourceConfig": {
        "ServiceBusConfigName": "Dispensing Work Record", //[section name with Dispensing Work Record service bus topic]
        "SystemName": "Kahler",
        "Direction": "Source"
    },
    "TargetConfig": {
        "ODataConfigName": "DynamicsAX", //[section name with F&O data configuration]
        "SystemName": "DynamicsAX",
        "Direction": "Target"
    },
    "DynamicsAX": {
        "UriString": [URL to D365 F&O],
        "ActiveDirectoryResource": [URL to D365 F&O],
        "ActiveDirectoryTenant": "https://login.microsoftonline.com/[Customer_Tenant_ID]",
        "ActiveDirectoryClientAppId": [Application ID used to register the application in AD],
        "ActiveDirectoryClientAppSecret": [Client Secret genrated for the Application ID in AD],
        "ODataEntityPath": "[URL to D365 F&O]/data/"
    },
    "Dispensing Work Record": {
        "ConnectionString": [connection string to Dispensing Work Record Topic],
        "TopicName": [Dispensing Work Record Topic Name],
        "SubscriptionName": [Subscription Name for Integration to D365 F&O],
        "RequiresSession": true
    }


## Agsync

## oneWeigh

## Field Reveal

## Surety

## Levridge Scale House