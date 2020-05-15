﻿# Configuring Controller Security

## Overview
Levridge has provided configurable security for our controllers. Once a controller is
secured each instance of the Integration Framework in which it is used must be 
configured in the Active Directory to expose the API.

[Here is a link](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-register-app) 
to the Microsoft documentation that explains the process of registering
an application in Azure Active Directory.

## Application Permissions (Roles)
Since controllers are generally called by applications that are not using the 
Azure Active Directory to authenticate users we have configured our controllers to
utilize [Application Permissions rather than Delegated permissions](https://docs.microsoft.com/en-us/azure/active-directory/develop/v2-permissions-and-consent#permission-types).

### Exposing Application Permissions
To expose application permissions you must add one or more roles to the registered application manifest.
Use [this link](https://docs.microsoft.com/en-us/azure/active-directory/develop/scenario-protected-web-api-app-registration#exposing-application-permissions-app-roles) 
for specific instructions. Don't forget to provide admin consent.

### Assigning Application Permissions
Once you have exposed application permissions you will need to assign those permissions
to the application that will be calling the API. You will assign Application Permissions 
as opposed to Delegated Permisions.

Use [this link](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-configure-app-access-web-apis#add-permissions-to-access-web-apis)
for specific instructions.

### Configuring Authorized Roles
Once the role(s) are defined as application permissions and the calling application is assigned
the necessary permissions you will need to add the [role(s)](./InstanceConfig.md#AcceptedApiRoles) to the [InstanceConfig](./InstanceConfig.md) [appsettings.json](./appsettings.json.md).

### Configure AzureAd Settings
You will need to provide the information necessary to utilize Azure AD to authenticate calls 
to the controller. See [AzureAd Settings](./AzureAd.md) for more information.

## Enabling Security on a Controller
At the time of this writing (5/15/2020) we only have security enabled on the default controller.

Be careful about enabling security on controllers. Many of the controllers are called by applcations
that expect anonymous access.

To enable security you will need to add the following attribute to the controller class:

    [Authorize(AuthenticationSchemes = OpenIdConnectDefaults.AuthenticationScheme + "," + JwtBearerDefaults.AuthenticationScheme)]
You can simply add the JwtBearer authentication scheme but then you will not be able to access
the API from a browser.

### Allowing Anonymous Access
If you have enabled security on a controller but you want certain actions to allow anonymous
access you can add the `[AllowAnonymous]` attribute to the method.

If you want all but a few actions to allow anonymous access you can simply add the
`[Authorize]` attribute only to the actions that you want to secure and don't add it 
to the class. Be sure to specify the Authentication Schemes you want to use or it will 
simply use the default which is OpenIdConnect.