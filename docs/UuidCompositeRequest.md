# UuidCompositeRequest
The UuidCompositeRequest object is used by the [AgsyncUUID](./AgsyncUUID.md) controller 
to make a request for UUID values based on SyncId values passed in the request.

# JSON Defintion
## JSON Example

    {
      "accountId": "ABC",
      "accountName": "Levridge - Barnesville",
      "growerId": "CUS-100442",
      "growerName": "Captain Cook Farms",
      "farmId": "COP100263",
      "farmeName": "Captain Cook Farms",
      "fieldId": "CST-400312",
      "fieldName": "CC Veggie Field NE"
    }

## JSON Schema

    {
        "$schema": "http://json-schema.org/draft-07/schema",
        "$id": "http://example.com/example.json",
        "type": "object",
        "readOnly": false,
        "writeOnly": false,
        "minProperties": 0,
        "title": "UuidCompositeRequest",
        "description": "This schema comprises the entire JSON document for a Composite Request",
        "additionalProperties": true,
        "required": [
            "accountId"
        ],
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
            "growerName": {
                "$id": "#/properties/growerName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The GrowerName Schema",
                "description": "This is an optional name for the Grower",
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
            "farmeName": {
                "$id": "#/properties/farmeName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FarmeName Schema",
                "description": "This is an optional name for the Farm",
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
            "fieldName": {
                "$id": "#/properties/fieldName",
                "type": "string",
                "readOnly": false,
                "writeOnly": false,
                "minLength": 0,
                "title": "The FieldName Schema",
                "description": "This is an optional name for the Field",
                "default": "",
                "examples": [
                    "NW 40"
                ]
            }
        }
    }

