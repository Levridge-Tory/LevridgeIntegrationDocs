

# Pricing Service Setup
The configuration for the pricing service setup is as follows:  


    {
     "clientappid": "[Client AppID from AD]",
     "clientappsecret": "[secret from AD]",
     "tenant": "https://login.microsoftonline.com/5555a5b1-fbt8-465b-ad9d-21e21129e610/oauth2/token",
     "uristring": "https://[environment subdomain].cloudax.dynamics.com/api/services/LevPricingServices/PricingService/getPricing",
     "resource": "https://[environment subdomain].cloudax.dynamics.com",
     "username": "John.smith@email.com",
     "password": "plaintextpassword"
    }
