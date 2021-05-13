## Deploying the Integration Framework
There are several ways to deploy the integration framework. Since the framework is a
standard [Azure App Service](https://azure.microsoft.com/en-us/services/app-service/)
we can use any of the deployment options available. The simplest deployment is to [deploy
a zip file](https://docs.microsoft.com/en-us/azure/app-service/deploy-zip).

Select one of the following options for more information on Deploying to Azure:

 - [Deploy as Zip file](./Deploy-Integration-Framework-as-Zip-File.md)
 - Deploy via FTP
 - Deploy with Script

The Integration Framework can also be [deployed as a Windows Service](Deploy-Integration-As-A-Service.md).

In order to integrate with D365 you must register the integration framework in Active Directory. 
Here are some articles that explain how to do that:
 - https://docs.microsoft.com/en-us/azure/active-directory/develop/howto-create-service-principal-portal
 - https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/use-single-tenant-server-server-authentication#azure-application-registration
 - https://docs.microsoft.com/en-us/azure/active-directory/azuread-dev/v1-protocols-oauth-code#register-your-application-with-your-ad-tenant

In order to access certain Azure resources like Azure Key Vault you will need to make sure your App Service
has a [system-assigned identity](https://docs.microsoft.com/en-us/azure/app-service/overview-managed-identity?tabs=dotnet#add-a-system-assigned-identity). 

## Next Steps

 - Create Service Bus 
 - [Configure the application](./ApplicationConfiguration)
 - 