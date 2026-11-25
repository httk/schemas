# import status (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/status`](https://schemas.httk.org/defs/v0.1/properties/imports/status.md)**  
**Definition name:** `status`

**Property name:** import status  
**Description:** The outcome of the import: "imported" when the thing was imported, "failed" when the import raised an error, and "excluded" when the importer deliberately did not import it.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](status.json)] [[MD](status.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/status",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import status",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "status",
        "label": "status_property_httk"
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
    "description": "The outcome of the import: \"imported\" when the thing was imported, \"failed\" when the import raised an error, and \"excluded\" when the importer deliberately did not import it.",
    "enum": [
        "imported",
        "failed",
        "excluded",
        null
    ]
}
```