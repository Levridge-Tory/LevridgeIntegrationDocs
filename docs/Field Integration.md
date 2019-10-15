# Field Integration
The Field integration is a unidirectional integration that receives messages to 
create a Levridge Customer Site using a configured Customer Site Type that represents
a customer field.

# Overview
The Field Integration API is a [Webhook](https://en.wikipedia.org/wiki/Webhook) that receives a posted message that is used
to create a new Customer Site in Levridge.

## API

### Authentication
What is the preferred way of using the API?

### Error Codes
What errors and status codes can a user expect?

### Rate limit
Is there a limit to the number of requests an user can send?

### Message Schema
    1 {
    2   "definitions": {},
    3   "$schema": "http://json-schema.org/draft-07/schema#",
    4   "$id": "http://schemas.levridge.com/field.json",
    5   "type": "object",
    6   "title": "Field Schema",
    7   "properties": {
    8     "growerID": {
    9       "$id": "#/properties/growerID",
    10       "type": "string",
    11       "title": "The Growerid Schema",
    12       "default": "",
    13       "examples": [
    14         "CUS-000071"
    15       ],
    16       "pattern": "^(.*)$"
    17     },
    18     "farmID": {
    19       "$id": "#/properties/farmID",
    20       "type": "string",
    21       "title": "The Farmid Schema",
    22       "description": "Used to populate the Customer Operation",
    23       "default": "",
    24       "examples": [
    25         "COP000010"
    26       ],
    27       "pattern": "^(.*)$"
    28     },
    29     "fieldID": {
    30       "$id": "#/properties/fieldID",
    31       "type": "string",
    32       "title": "The Fieldid Schema",
    33       "description": "Used to populate the Customer Site Code",
    34       "default": "",
    35       "examples": [
    36         "CST-000150"
    37       ],
    38       "pattern": "^(.*)$"
    39     },
    40     "fieldName": {
    41       "$id": "#/properties/fieldName",
    42       "type": "string",
    43       "title": "The Fieldname Schema",
    44       "description": "The name of the field",
    45       "default": "",
    46       "examples": [
    47         "Test Field Type"
    48       ],
    49       "pattern": "^(.*)$"
    50     },
    51     "farmableAcres": {
    52       "$id": "#/properties/farmableAcres",
    53       "type": "number",
    54       "title": "The Farmableacres Schema",
    55       "default": 0.0,
    56       "examples": [
    57         19.5
    58       ]
    59     }
    60   },
    61   "required": [
    62     "farmID",
    63     "fieldID",
    64     "fieldName"
    65   ]
    66 }


## Configuration
