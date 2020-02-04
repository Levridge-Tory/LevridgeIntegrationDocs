<!-- 
Add instance config reference
Add service bus setup reference (move from bottom)
Specify Hostfile with info for background task
Specific documentation for what Entities to setup in F&O. Include information on filtering customers, operations & sites
  -- Caveat on dependent entities will not necessarily be changed so they won't trigger change control
Add reference to azure key vault setup
Change CRM instructions to Create & Deploy CDS solution
Document Agsync JSON object
Document BOM setup in F&O
-->

## Agsync
The Agsync integration is a bidirectional integration that consists of a Topic for
Master Data that goes from D365 F&O to Agsync and Service Calls for Work Orders that go from 
Agsync to D365 F&O. Because the Work Orders utilize a direct service call to F&O there is no
need for two integration instances.

One aspect of the Agsync integration that is different from other integrations is the 
service call to D365 F&O for work orders.

Another aspect that is different is that we are using CDS to provide lookup services for 
mapping entity identifiers between systems.

We also need to filter the customers that are sent from F&O to Agsync. This will require configuring
a filter on the event in F&O. 

### Setup
To integrate from D365 F&O to Agsync you will need to:

 - [Create an Azure Service bus topic](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-quickstart-topics-subscriptions-portal)
 - [Create a subscription on the topic above](https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-quickstart-topics-subscriptions-portal)
 - [Configure Event Endpoint in F&O](./Configuring-Levridge-Entity-Event-Endpoint.md)
 - [configure Levridge Entity Events](./Configuring-Levridge-Entity-Events.md)
   - Create Filter on Entity Event to only send agronomy customers 
   <!-- TODO: Document how to create filter -->
 - Get Client ID and CLient password from Agsync
 - Get Customer Specific Integration ID from Agsync
 - Client Redirect URL is [Azure Webapp base URL]/api/AgsyncAuth
 - [Setup Azure Keyvault](./AzureKeyVault.md) 
 - [Create an application ID](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) for the integration framework to authenticate to D365 CRM
 - [Create an application user in D365 CRM](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/use-multi-tenant-server-server-authentication#create-an-application-user--associated-with-the-registered-application--in-) and assign the proper role(s)


### Configuration
In the appsettings.json you will need to define the [InstanceConfig](./InstanceConfig.md)  [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:

      "InstanceConfig": {
        "AzureTableConfiguration": "[section name to Azure Table Configuration",
        "LogRequestsAndResponses": [true or false]
        "EnableAppInsightsAdaptiveSampling": [true or false]
      },
      "SourceConfig": {
        "ServiceBusConfigName": "[section name with service bus topic and subscription for Agsync Master Data]",
        "ODataConfigName": "[section name with F&O data configuration]",
        "SystemName": "DynamicsAx",
        "Direction": "Source"
      },
      "TargetConfig": {
        "ODataConfigName": "[section name with Agsync endpoint configuration]",
        "CDSConfigName": "[section name with CDS data configuration]",
        "SystemName": "AgSync",
        "Direction": "Target",
      }

You must also include the controller entry to have the controller loaded:

    "Controllers": {
        "HostController": "Levridge.Integration.Host.DefaultController",
        "AgSyncConroller": "Levridge.Integration.Host.AgSyncController"
    }

You must also configure the 

Here is a sample template for the entire appsettings.json file used for the integration
from FinOps to Agsync:

    {
        "Controllers": {
            "HostController": "Levridge.Integration.Host.DefaultController",
            "AgSyncConroller": "Levridge.Integration.Host.AgSyncController"
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
            "ServiceBusConfigName": "AgsyncMasterDataServiceBus",
            "ODataConfigName": "DynamicsAX",
            "SystemName": "DynamicsAx",
            "Direction": "Source"
        },
        "TargetConfig": {
            "ODataConfigName": "AgSyncEndpoint",
            "SystemName": "AgSync",
            "Direction": "Target",
            "CDSConfigName": "CDS"
        },
        "DynamicsAX": {
            "UriString": "[URL to D365 F&O]",
            "ActiveDirectoryResource": "[URL to D365 F&O]",
            "ActiveDirectoryTenant": "https://login.microsoftonline.com/[Customer_Tenant_ID]",
            "ActiveDirectoryClientAppId": "[Application ID used to register the application in AD]",
            "ActiveDirectoryClientAppSecret": "[Client Secret generated for the Application ID in AD]",
            "ODataEntityPath": "[URL to D365 F&O]/data/"
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
        "AgSyncEndpoint": {
            "baseUri": "https://fields.agsync.com/api/",
            "tokenUrl": "https://auth.agsync.com/core/connect/token",
            "ClientId": "[client ID assigned by Agsync]", // customer specific
            "ClientPass": "[Client Secret assigned by Agsync]", // customer specific
            "ValutURL": "[URL to customer Azure Key Vault]",
            "AgSyncTokenKey": "AgsyncAccessToken",
            "RedirectUri": "[URL to AgsyncAuth controller]", // customer specific
            "IntegrationId": "CustomerIntegrationID" // customer specific
        },
        "agsync": { // used by Webhook
            "ConnectionString": "[connection string to Agsync master data topic]",
            "TopicName": "[Agsync master data topic]",
            "RequiresSession": true,
            "RedirectUri": "[URL to AgsyncAuth controller]",
            "TokenUrl": "https://auth.agsync.com/core/connect/token",
            "AuthorizeUrl": "https://auth.agsync.com/core/connect/authorize",
            "baseUri": "https://fields.agsync.com/api/",
            "ClientId": "[client ID assigned by Agsync]",
            "ClientPass": "[Client Secret assigned by Agsync]",
            "ValutURL": "[URL to customer Azure Key Vault]",
            "AgSyncTokenKey": "AgsyncAccessToken"
        },
        "AgsyncMasterDataServiceBus": {
            "ConnectionString": "[connection string to Agsync master data topic]",
            "TopicName": "[Agsync master data topic]",
            "SubscriptionName": "[Agsync master data subscription name]",
            "RequiresSession": true
        }
    }
