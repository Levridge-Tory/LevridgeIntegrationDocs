# UuidCompositResponse
The UuidCompositResponse object is used by the [AgsyncUUID](./AgsyncUUID.md) controller 
to return UUID values based on SyncId values passed in the request.

# JSON Defintion
## JSON Example

    {      
        "accountId": "BAR",
        "accountUuid": "336a8049-853c-4992-8382-e77e8868e208",
        "accountGuid": "000ad538-0000-0000-0000-000000000000",
        "accountName": null,
        "growerId": "CUS-100442",
        "growerUuid": "63ffb30a-aaf6-4cbe-83b7-95765aa2c5e4",
        "growerGuid": "000ceb06-0000-0000-0000-000000000000",
        "growerName": null,
        "farmId": "COP100263",
        "farmUuid": "d4334cd1-1a1f-4484-94d6-246645e07196",
        "farmGuid": "000ceb07-0000-0000-0000-000000000000",
        "farmName": null,
        "fieldId": "CST-400312",
        "fieldUuid": "9e0f0647-c21a-495a-92a2-9d0aaaf2bc8f",
        "fieldGuid": "001a5c8a-0000-0000-0000-000000000000",
        "fieldName": null
    }

## JSON Schema

    {
        "$schema": "http://json-schema.org/draft-07/schema",
        "$id": "http://example.com/example.json",
        "type": "object",
        "readOnly": false,
        "writeOnly": false,
        "minProperties": 0,
        "title": "The UuidCompositeResponse Schema",
        "description": "The root schema comprises the entire JSON document for Composite Response",
        "additionalProperties": true,
        "required": [],
        "properties": {
            "accountId": {
                "$id": "#/properties/accountId",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The AccountId Schema",
                "description": "The Sync Id for the Account (FinOps Branch)",
                "default": "",
                "examples": [
                    "SCG1"
                ]
            },
            "accountUuid": {
                "$id": "#/properties/accountUuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The AccountUuid Schema",
                "description": "The UUID for the Account (FinOps Branch)",
                "default": "",
                "examples": [
                    "e0485a5d-f6c1-4a0e-824a-1abffbcfaa9"
                ]
            },
            "accountGuid": {
                "$id": "#/properties/accountGuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The AccountGuid Schema",
                "description": "The GUID for the Account (FinOps Branch)",
                "default": "",
                "examples": [
                    "000c33a4-0000-0000-0000-000000000000"
                ]
            },
            "accountName": {
                "$id": "#/properties/accountName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The AccountName Schema",
                "description": "This is an optional name for the account",
                "default": "",
                "examples": [
                    "Alexandria"
                ]
            },
            "growerId": {
                "$id": "#/properties/growerId",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The GrowerId Schema",
                "description": "The Sync Id for the Grower (FinOps Customer)",
                "default": "",
                "examples": [
                    "CUS-100347"
                ]
            },
            "growerUuid": {
                "$id": "#/properties/growerUuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The GrowerUuid Schema",
                "description": "The UUID for the Grower (FinOps Customer)",
                "default": "",
                "examples": [
                    "ad5ee735-c783-45d3-9b7a-5e7b089b1fbf"
                ]
            },
            "growerGuid": {
                "$id": "#/properties/growerGuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The GrowerGuid Schema",
                "description": "The GUID for the Grower (FinOps Customer)",
                "default": "",
                "examples": [
                    "000cd991-0000-0000-0000-000000000000"
                ]
            },
            "growerName": {
                "$id": "#/properties/growerName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The GrowerName Schema",
                "description": "This is an optional name for the grower",
                "default": "",
                "examples": [
                    "Bjorklund Land & Cattle"
                ]
            },
            "farmId": {
                "$id": "#/properties/farmId",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FarmId Schema",
                "description": "The Sync Id for the Farm (FinOps Customer Operation)",
                "default": "",
                "examples": [
                    "COP100208"
                ]
            },
            "farmUuid": {
                "$id": "#/properties/farmUuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FarmUuid Schema",
                "description": "The UUID for the Grower (FinOps Customer Operation)",
                "default": "",
                "examples": [
                    "1f7b3ecc-e2eb-4724-b9ec-f0b756d21566"
                ]
            },
            "farmGuid": {
                "$id": "#/properties/farmGuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FarmGuid Schema",
                "description": "The GUID for the Farm (FinOps Customer Operation)",
                "default": "",
                "examples": [
                    "000cd992-0000-0000-0000-000000000000"
                ]
            },
            "farmeName": {
                "$id": "#/properties/farmeName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FarmeName Schema",
                "description": "This is an optional name for the farm",
                "default": "",
                "examples": [
                    "Bjorklund Land & Cattle"
                ]
            },
            "fieldId": {
                "$id": "#/properties/fieldId",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FieldId Schema",
                "description": "The Sync Id for the Field (FinOps Customer Site)",
                "default": "",
                "examples": [
                    "CST-000026"
                ]
            },
            "fieldUuid": {
                "$id": "#/properties/fieldUuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FieldUuid Schema",
                "description": "The UUID for the Field (FinOps Customer Site)",
                "default": "",
                "examples": [
                    "2ac15a5a-2c8a-4f65-b5fe-3706637937ec"
                ]
            },
            "fieldGuid": {
                "$id": "#/properties/fieldGuid",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FieldGuid Schema",
                "description": "The GUID for the Field (FinOps Customer Site)",
                "default": "",
                "examples": [
                    "001a4769-0000-0000-0000-000000000000"
                ]
            },
            "fieldName": {
                "$id": "#/properties/fieldName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FieldName Schema",
                "description": "This is an optional name for the field",
                "default": "",
                "examples": [
                    "NW 40"
                ]
            }
        }
    }