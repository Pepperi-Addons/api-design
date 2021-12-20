# Transaction Object
```json
[{
    "AccountUUID":"ec8686af-17e4-41e0-94d4-28e1f5237d9a",
    "ATDID":"",
    "Remark":"",
    "TransactionLines": [
        {
            "UnitsQuantity": 3,
            "ItemUUID":"",
            "Price": 0,
        }
    ]
}]
```

# Exported Transaction Object
``` json
{
    "Objects": [{
        "AccountUUID":"ec8686af-17e4-41e0-94d4-28e1f5237d9a",
        "ATDID":"",
        "Remark":"",
        "TransactionLines": [
            {
                "UnitsQuantity": 3,
                "ItemUUID":"",
                "Price": 0,
            }
        ]
    }],
    "References": {
        "Accounts": {
            "ec8686af-17e4-41e0-94d4-28e1f5237d9a": {

            }
        },
        "Types": {

        },
        "Items": {

        }
    }
}
```

# Transaction Scheme
``` json
{
    "Fields": {
        "AccountUUID": {
            "Type": "Resource",
            "ResourceName": "Accounts",

            // optional
            // if none exists and there is one relation of Accounts
            // then the relation will be used
            "AddonUUID": ""
        },
        "ATDID": {
            "Type": "Resource",
            "ResourceName": "Types",
            "AddonUUID": "{papi}"
        },
        "Remark": {
            "Type": "String",
        },
        "TransactionLines": {
            "Type": "Array",
            "Items": {
                "Type": "Object",
                "Fields": {
                    "UnitsQuantity": {
                        "Type": "Number",
                    },
                    "ItemUUID": {
                        "Type": "Resource",
                        "ResourceName": "Items",
                        "AddonUUID": "{papi}"
                    },
                    "Price": {
                        "Type": "Number",
                    },
                }
            }
        }
    }
}
```