# AgsyncUUID Controller
The AgsyncUUID controller returns Agsync UUID values based on SyncIds provided to the controller.

# Overview
The AgsyncUUID controller has one GET method and two POST methods. 

## GET Method
The GET method in the form of [BaseURL]/api/AgsyncUUID/[recordType]/[id]. 
The valid record types are:
 - Account
 - Grower
 - Farm
 - Field

## POST Methods
The two POST methods both take a UuidCompositeRequest and return UuidCompositeResponse 
as a response. One URL accepts a record type (one of the valid strings above) in the 
form of [BaseURL]/api/AgsyncUUID/[recordType] with a [UuidCompositeRequest](./UuidCompositeRequest.md) 
in the body. 

This action will populate the [UuidCompositeResponse](./UuidCompositeResponse.md) in a hierarchical 
manner. For example, if the record type is "Account" only the account values will be returned. 
If the record type is "Grower" then the grower and account values will be returned. 
If the record type is "Field" then all record values will be returned.

The second POST does not take a record type. It will simply take a [UuidCompositeRequest](./UuidCompositeRequest.md) 
in the body and will populate the values for any non-empty ID. 
For example, if the UuidCompositeRequest.AccountId and the UuidCompositeRequest.FieldId 
have values their respective identifying values will be returned in the [UuidCompositeResponse](./UuidCompositeResponse.md). 

If there are any errors, they will always be reported in the UuidCompositResponse.FieldName value.
