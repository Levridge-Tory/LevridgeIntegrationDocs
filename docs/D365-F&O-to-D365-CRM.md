## D365 F&O to D365 CRM

### Setup
To integrate from D365 F&O to D365 CRM you will need to:
 - [Configure Event Endpoint in F&O](./Configuring-Levridge-Entity-Event-Endpoint.md) 
 - [configure Levridge Entity Events](./Configuring-Levridge-Entity-Events.md)
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

