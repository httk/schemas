# import error (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/error`](https://schemas.httk.org/defs/v0.1/properties/imports/error.md)**  
**Definition name:** `error`

**Property name:** import error  
**Description:** The exception or exclusion text of a failed or excluded import; null when the thing was imported.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](error.json)] [[MD](error.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/error",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import error",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "error",
        "label": "error_property_httk"
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
    "description": "The exception or exclusion text of a failed or excluded import; null when the thing was imported."
}
```