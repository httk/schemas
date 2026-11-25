# import time (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/imported_at`](https://schemas.httk.org/defs/v0.1/properties/imports/imported_at.md)**  
**Definition name:** `imported_at`

**Property name:** import time  
**Description:** When the import was made, as a timezone-aware timestamp, if recorded.  
**Type:** timestamp  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**

- `"2007-04-05T14:30:20Z"`

**Formats:** [[JSON](imported_at.json)] [[MD](imported_at.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/imported_at",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import time",
    "x-optimade-type": "timestamp",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "imported_at",
        "label": "imported_at_property_httk"
    },
    "x-optimade-unit": "inapplicable",
    "x-optimade-requirements": {
        "support": "may",
        "sortable": true,
        "query-support": "all mandatory",
        "response-level": "may"
    },
    "type": [
        "string",
        "null"
    ],
    "format": "date-time",
    "description": "When the import was made, as a timezone-aware timestamp, if recorded.",
    "examples": [
        "2007-04-05T14:30:20Z"
    ]
}
```