# Kahler Integration
The Kahler integration is a bidirectional integration that consists of a Topic for
Dispensing Work Orders that go from D365 F&O to Kahler and Dispensing Work Records that go from 
Kahler to D365 F&O. 


# Overview
Because this is a bidirectional integration there are two instances of the integration running
to handle the entire integration. There is one integration instance for each direction.

One aspect of Kahler that is different from other integrations is the D365 F&O to Kahler
instance must run on premise because the Kahler system runs behind the firewall. This
should be deployed as a service.

Another aspect that is different is that each location should only get the messages from the 
topic that apply to that location. This is done with a filter on the service bus topic subscription.
In order for the filter to work the Levridge Entity Event must be configured to expose
the branch property on the message.

## Setup
To integrate to and from Kahler and D365 F&O you will need to:
 
 - [Configure Event Endpoint in F&O](./Configuring-Levridge-Entity-Event-Endpoint.md)
 - [Configure Levridge Entity Events]("./Configuring-Levridge-Entity-Events.md")
   - You will need to be sure to provide properties on the event to allow filtering by Branch
 - [Create an application ID](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) for the integration framework to authenticate to D365 F&O
 - [Create an Azure Active Directory Application in D365 F&O](https://docs.microsoft.com/en-us/dynamics365/unified-operations/dev-itpro/data-entities/services-home-page#authentication)
 - Create an Azure Service bus topic for Dispensing Work Orders (D365 F&O to Kahler)
 - Create an Azure Service bus topic for Dispensing Work Records (Kahler to D365 F&O)
 - Create a subscription on the Dispensing Work Order topic for each Branch that has a Kahler mixer
 - Create a filter on the subscription for each Branch
 - Create a subscription on the Dispensing Work Record topic for integration back to F&O
 - [Deploy the Levridge Integration Framework as a service](./Deploy-Integration-As-A-Service.md) at each Branch that has a Kahler mixer

## Configuration for Kahler on Premise
This configuration will need to be on premise with the Kahler mixer. The on-premise instance
will handle the Dispensing Work Order from D365 F&O to Kahler  and the Webhook that receives
Dispensing Work Records from Kahler.

In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

        "SourceConfig": {
            "ServiceBusConfigName": "[section name with Dispensing Work Order service bus topic]",
            "ODataConfigName": "[section name with F&O data configuration]",
            "SystemName": "DynamicsAX",
            "Direction": "Source"
        },
        "TargetConfig": {
            "ODataConfigName": "[section name with Kahler data configuration]",
            "CDSConfigName": "[section name with CDS data configuration]",
            "SystemName": "Kahler",
            "Direction": "Target"
        }

Here is a sample template for the entire appsettings.json file used for the on-premise deployemnt
of the integration from FinOps to Kahler:

    {
        "Controllers": {
            "HostController": "Levridge.Integration.Host.DefaultController",
            "KahlerConroller": "Levridge.Integration.Host.KahlerController"
        },
        "Logging": {
            "Debug": {
                "LogLevel": {
                    "Default": "Information"
                }
            },
            "Console": {
                "IncludeScopes": true,
                "LogLevel": {
                    "Default": "Information"
                }
            },
            "LogLevel": {
                "Default": "Information"
            }
        },
        "AllowedHosts": "*",
        "SourceConfig": {
            "ServiceBusConfigName": "Dispensing Work Order", //[section name with Dispensing Work Order service bus topic]
            "ODataConfigName": "DynamicsAX", //[section name with F&O data configuration]
            "SystemName": "DynamicsAX",
            "Direction": "Source"
        },
        "TargetConfig": {
            "ODataConfigName": "Kahler End Point", //[section name with Kahler data configuration],
            "CDSConfigName": "[section name with CDS data configuration]",
            "SystemName": "Kahler",
            "Direction": "Target"
        },
        "DynamicsAX": {
            "UriString": "[URL to D365 F&O]",
            "ActiveDirectoryResource": "[URL to D365 F&O]",
            "ActiveDirectoryTenant": "https://login.microsoftonline.com/[Customer_Tenant_ID]",
            "ActiveDirectoryClientAppId": "[Application ID used to register the application in AD]",
            "ActiveDirectoryClientAppSecret": "[Client Secret generated for the Application ID in AD]",
            "ODataEntityPath": "[URL to D365 F&O]/data/"
        },
        "Kahler End Point": {
            "UriString": "[URL to Local Kahler]"
        },
        "Dispensing Work Order": {
            "ConnectionString": "[connection string to Dispensing Work Order Topic]",
            "TopicName": "[Dispensing Work Order Topic Name]",
            "SubscriptionName": "[Subscription Name for the Branch]",
            "RequiresSession": true
        },
        "CDS": {
            "UriString": "[URL to CDS or Localhost]",
            "ActiveDirectoryResource": "[URL to CDS]",
            "ActiveDirectoryTenant": "https://login.microsoftonline.com/[Customer_Tenant_ID]",
            "ActiveDirectoryClientAppId": "[Application ID used to register the application in AD]",
            "ActiveDirectoryClientAppSecret": "[Client Secret generated for the Application ID in AD]",
            "ODataEntityPath": "[URL to CDS]/api/data/v9.0/",
            "AssemblyName": "Levridge.ODataDataSources.CDS",
            "ClientClassesNameSpace": "Levridge.ODataDataSources.CDS",
            "MetadataResource": "CDSMetadata.xml"
        },
        "Levridge.Integration.Host.KahlerController": {
            "ConnectionString": "[connection string to Dispensing Work Record Topic]",
            "TopicName": "[Dispensing Work Record Topic Name]",
            "RequiresSession": true
        }
    }

### Controllers
This section contains a list of controllers that will be loaded by the current instance. In addition to the default 
controller that we always want to load, we want the system to load the Kahler controller. The names (on the left) are not
significant and are used only for debugging. The values (on the right) are significant. It must be the name of the assembly
that should be loaded for the controller.

### [SourceConfig](./SourceConfig.md)
The source config will represent the data being send from D365 F&O. Currently, the Dispensing Work Order is the only entity
sent from F&O. In the future the topic may also include master data that is sent to Kahler.

The ODataConfigName is not currently being used but is a required value. So point it to the section that contains the connection
information to D365 F&O.

### [TargetConfig](./TargetConfig.md)
The target config will represent the data endpoint for the local Kahler mixer. The "ODataConfigName" should point to a section
that contains the Kahler REST endpoint.

### Levridge.Integration.Host.KahlerController
This section is used by the Kahler controller to be able to send messages to the proper topic to be handled by the integration
framework and written to D365 F&O

## Configuration for Kahler in Azure
This instance can be a single instance running in the cloud. This instance will handle 
the Dispensing Work Record from Kahler to D365 F&O

In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

        "SourceConfig": {
            "ServiceBusConfigName": "[section name with Dispensing Work Record service bus topic]"
            "ODataConfigName": "",
            "SystemName": "Kahler",
            "Direction": "Source"
        },
        "TargetConfig": {
            "ODataConfigName": "[section name with F&O data configuration]",
            "CDSConfigName": "[section name with CDS configuration]",
            "SystemName": "DynamicsAX",
            "Direction": "Target"
        }

Here is a template of the full appsettings.json file used for the Kahler integration from the Webhook to FinOps:

    {
        "Controllers": {
            "HostController": "Levridge.Integration.Host.DefaultController"
        },
        "Logging": {
            "Debug": {
                "LogLevel": {
                    "Default": "Information"
                }
            },
            "Console": {
                "IncludeScopes": true,
                "LogLevel": {
                    "Default": "Information"
                }
            },
            "LogLevel": {
                "Default": "Information"
            }
        },
        "AllowedHosts": "*",
        "SourceConfig": {
            "ServiceBusConfigName": "Dispensing Work Record", //[section name with Dispensing Work Record service bus topic]
            "ODataConfigName": "",
            "SystemName": "Kahler",
            "Direction": "Source"
        },
        "TargetConfig": {
            "ODataConfigName": "DynamicsAX", //[section name with F&O data configuration]
            "CDSConfigName": "CDS",
            "SystemName": "DynamicsAX",
            "Direction": "Target"
        },
        "DynamicsAX": {
            "UriString": "[URL to D365 F&O]",
            "ActiveDirectoryResource": "[URL to D365 F&O]",
            "ActiveDirectoryTenant": "https://login.microsoftonline.com/[Customer_Tenant_ID]",
            "ActiveDirectoryClientAppId": "[Application ID used to register the application in AD]",
            "ActiveDirectoryClientAppSecret": "[Client Secret generated for the Application ID in AD]",
            "ODataEntityPath": "[URL to D365 F&O]/data/"
        },
        "Dispensing Work Record": {
            "ConnectionString": "[connection string to Dispensing Work Record Topic]",
            "TopicName": "[Dispensing Work Record Topic Name]",
            "SubscriptionName": "[Subscription Name for Integration to D365 F&O]",
            "RequiresSession": true
        }
    }
