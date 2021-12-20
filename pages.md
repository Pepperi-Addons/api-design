``` json
{
    "Hidden": false,
    "CreationDateTime": "2021-07-22T13:00:11.360Z",
    "ModificationDateTime": "2021-07-22T13:00:11.360Z",
    "Key": "610bdf75-d66e-4126-bfc4-0bb74eeabcab",
    "Name": "MyPage",
    "Description": "",
    "Type": "Home", 
    "Blocks": [
        {
            "Key": "99dfdff5-d042-4f4b-94ec-1d4fb238adba",
            "Relation": {
                "Name": "",
                "SubType": "Ng12",
                "AddonUUID": "a6f4fd84-d539-41a5-9ff6-946bddebf4d1",
                "AddonRelativeURL": "/addon_block",
                "ModuleName": "MyModule",
                "ComponentName": "MyComponent"
            },
            "Configuration": {
                "Title": {
                    "TextSize": "1.5em",
                },

                "Query": {
                    "ResourceName": "DataQueries",
                    // "AddonUUID": "",
                    "Key": "",
                }
            },
            "PageConfiguration": {
                "Consume": {
                    "Filter": {
                        "Resource": "transaction_lines",
                        "Fields":  ["UnitsQuantity", "Item.TSABrand", "Transaction.Account.Type", "Transaction.Status"]
                    },
                    
                    "Context": {
                        "Resource": "transaction"
                    }
                },
                "Produce": {
                    "Filters": [
                        {
                            "Resource": "transaction",
                            "Fields":  ["UnitsQuantity", "Item.TSABrand", "Transaction.Account.Type", "Transaction.Status"],
                        }
                    ],
                    
                    "Context": {
                        "Resource": "transaction_lines"
                    }
                }
            }
        }
    ],

    // A list of sections in the page
    "Layout": {
        "Sections": [
            {
                // The unique key of the section
                // mandatory
                "Key": "99dfdff5-d042-4f4b-94ec-1d4fb238adba",
                
                // the name of the section
                // to be shown in the UI
                "Name": "",
            
                // The fixed height
                // or min height when IsHeightFixed=false
                // The units is rem
                "Height": 350,
                
                // How do the columns split in the section
                // For 1 part this must be empty
                // For 2 parts this must be "1/2 1/2" | "1/3 2/3" | "2/3 1/3"
                // For 3 parts this must be "1/3 1/3 1/3" | "1/2 1/4 1/4" | "1/4 1/2 1/4" | "1/4 1/4 1/2"
                // For 4 parts this must be "1/4 1/4 1/4 1/4" etc.
                "Split": "",
    
                // The blocks in the section LTR
                "Columns": [
                    {
                        // optional - default empty column
                        "Block": {                        
                            "Key": "99dfdff5-d042-4f4b-94ec-1d4fb238adba",
    
                            // Hide the block in certain screen sizes
                            // default is empty array
                            "Hide": ["Desktop", "Tablet", "Mobile"]
                        }
                    }
                ],

                // Hide the section in certain screen sizes
                // default is empty array
                "Hide": ["Tablet", "Phablet", "Landscape"]
            }
        ],

        // The Gap between the sections
        // optional - default is None (no gap)
        "SectionsGap": "SM|MD|LG|None",

        // The Gap between the column in the sections
        // optional - default is None (no gap)
        "CoulmnsGap": "SM|MD|LG|None",

        // The Spacing to the left and right of the page
        "HorizontalSpacing": "SM|MD|LG|None",

        // The Spacing to the top and bottom of the page
        "VerticalSpacing": "SM|MD|LG|None",

        // nonexisting or 0 - is 100%
        // in pixel
        "MaxWidth": 1200
    }
}
```