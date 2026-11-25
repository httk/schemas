# import repaired (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/repaired`](https://schemas.httk.org/defs/v0.1/properties/imports/repaired.md)**  
**Definition name:** `repaired`

**Property name:** import repaired  
**Description:** Whether the importer had to repair the source to import it. Only an imported thing can have been repaired.  
**Type:** boolean  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](repaired.json)] [[MD](repaired.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/repaired",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import repaired",
    "x-optimade-type": "boolean",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "repaired",
        "label": "repaired_property_httk"
    },
    "x-optimade-unit": "inapplicable",
    "x-optimade-requirements": {
        "support": "may",
        "sortable": true,
        "query-support": "all mandatory",
        "response-level": "may"
    },
    "type": [
        "boolean",
        "null"
    ],
    "description": "Whether the importer had to repair the source to import it. Only an imported thing can have been repaired."
}
```