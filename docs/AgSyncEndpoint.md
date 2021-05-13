# AgSyncEndpoint Settings
AgSyncEndpoint is an object in the appsettings.json file used by the Levridge Integration Framework
to define the configuration for the integration between FinOps and Agsync master data.


# Example
    "AgSyncEndpoint": {
      "MustUseWktProcessor": true,
      "UuidSource": "Agsync",
      "BaseFieldUri": "https://fields.agsync.com/api/",
      "BaseOrderUri": "https://orders.agsync.com/api/",
      "tokenUrl": "https://auth.agsync.com/core/connect/token",
      "ClientId": "[Agsync assigned client ID]",
      "ClientPass": "[Agsync assigned client password]",
      "VaultURL": "https://levridgeagsynckeyvault.vault.azure.net/",
      "AgSyncTokenKey": "AgsyncAccessToken",
      "RedirectUri": "[Agsync Integration Base URL]/api/AgsyncAuth",
      "IntegrationId": "[Agsync assigned integration Id]"
    }

# Definition
## UuidSource

## BaseFieldUri

## BaseOrderUri

## tokenUrl

## ClientId

## ClientPass

## VaultURL

## AgSyncTokenKey

## RedirectUri

## IntegrationId