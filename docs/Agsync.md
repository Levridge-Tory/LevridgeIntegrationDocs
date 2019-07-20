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

 - [Configure Event Endpoint in F&O](./Configuring-Levridge-Entity-Event-Endpoint.md)
 - [configure Levridge Entity Events](./Configuring-Levridge-Entity-Events.md)
   - Create Filter on Entity Event to only send agronomy customers 
   <!-- TODO: Document how to create filter -->
 - Get Client ID and CLient password from Agsync
 - Get Customer Specific Integration ID from Agsync
 - Client Redirect URL is [Azure Webapp base URL]/api/AgsyncAuth
 - Setup Azure Keyvault 


 - [Create an application ID](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) for the integration framework to authenticate to D365 CRM
 - [Create an application user in D365 CRM](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/use-multi-tenant-server-server-authentication#create-an-application-user--associated-with-the-registered-application--in-) and assign the proper role(s)
 - Create an Azure Service bus topic
 - Create a subscription on the topic above


### Configuration
In the appsettings.json you will need to define the [SourceConfig](./SourceConfig.md) and [TargetConfig](./TargetConfig.md) nodes as follows:
