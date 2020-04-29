# agsync Settings
agsync is an object in the appsettings.json file used by the Levridge Integration Framework
to define the configuration for the integration of Agsync Workorders to FinOps.


# Example
    "agsync": {
      "MustUseWktProcessor": true,
      "ConnectionString": "Endpoint=[Customer Servicebus Connection String]",
      "TopicName": "[Customer Servicebus Topic]",
      "SubscriptionName": "[Customer Servicebus Topic Subscription]",
      "PrefetchCount": 5,
      "RequiresSession": [true/false],
      "RedirectUri": "[Agsync Integration Base URL]/api/AgsyncAuth",
      "TokenUrl": "https://auth.agsync.com/core/connect/token",
      "AuthorizeUrl": "https://auth.agsync.com/core/connect/authorize",
      "baseUri": "https://fields.agsync.com/api/",
      "rejectUri": "https://orders.agsync.com/api/orders/",
      "ClientId": "[Agsync assigned client ID]",
      "ClientPass": "[Agsync assigned client password]",
      "VaultURL": "[Integration Framework Key Vault URL]",
      "AgSyncTokenKey": "[Vault Key Used for Access Token]"
      "WktUrl": "[Agsync Integration Base URL]/api/WktProcessor",
      "ProcessStatuses": "Plan,Released,Canceled,Scheduled,Rejected,Completed,Accepted",
      "MustUseCustomerSite": true
    }

# Definition

## MustUseWktProcessor
The MustUseWktProcessor attribute contains a bollean that specifies whether or not to 
process the WKT sent in the workorder from Agsync to FinOps.

## ConnectionString

## TopicName

## SubscriptionName

## PrefetchCount

## RequiresSession

## RedirectUri

## TokenUrl

## AuthorizeUrl

## baseUri

## rejectUri

## ClientId

## ClientPass

## VaultURL

## AgSyncTokenKey

## ProcessStatuses
**Not Required**

Place a comma delimited list of statuses that should be processed by the controller.
It is important to make sure the capitalization is correct (Title Case) because it does
an exact match.

**Deafult:**
"Planned,Released,Canceled,Scheduled,Rejected,Completed,Accepted"

## MustUseCustomerSite
**Not Required**

Set this value to `true` to require a valid customer site on work orders.
Set this value to `false` to ignore the customer site on work orders.

**Default:**
true