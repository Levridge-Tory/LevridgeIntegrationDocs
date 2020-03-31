# Configure Authentication

## Register your application

To register your application and manually add the app's registration information to your solution, follow these steps:

1. Sign in to the Azure portal using either a work or school account, or a personal Microsoft account.

2. If your account gives you access to more than one tenant, select your account in the top right corner, and set your portal session to the desired Azure AD tenant.

3. Navigate to the Microsoft identity platform for developers App registrations page.

4. Select New registration.

5. When the Register an application page appears, enter your application's registration information:
    * In the Name section, enter a meaningful application name that will be displayed to users of the app, for example AspNetCore-Quickstart.
    
    * In Redirect URI, add https://localhost:44321/, and select Register.

6. Select the Authentication menu, and then add the following information:

    * In Redirect URIs, add https://localhost:44321/signin-oidc, and select Save.

    * In the Advanced settings section, set Logout URL to https://localhost:44321/signout-oidc.

    * Under Implicit grant, check ID tokens.

    * Select Save.

7. Create a section in Appsettings.json named **AzureAd**.

```json
    "AzureAd": {
        "Instance": "https://login.microsoftonline.com/",
        "Domain": "yourdomain.com",
        "TenantId": "00000000-0000-0000-0000-000000000000",
        "ClientId": "00000000-0000-0000-0000-000000000000",
        "CallbackPath": "/signin-oidc"
    }
```

Taken from [Quickstart: Add sign-in with Microsoft to an ASP.NET Core web app](https://docs.microsoft.com/en-us/azure/active-directory/develop/quickstart-v2-aspnet-core-webapp#option-2-register-and-manually-configure-your-application-and-code-sample).