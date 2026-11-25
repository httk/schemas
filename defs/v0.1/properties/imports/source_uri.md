# import source URI (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/source_uri`](https://schemas.httk.org/defs/v0.1/properties/imports/source_uri.md)**  
**Definition name:** `source_uri`

**Property name:** import source URI  
**Description:** Where the imported thing was imported from, as chosen by the importer: a stable path, URL, or identifier, not a machine-specific absolute path.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](source_uri.json)] [[MD](source_uri.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/source_uri",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import source URI",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "source_uri",
        "label": "source_uri_property_httk"
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
    "description": "Where the imported thing was imported from, as chosen by the importer: a stable path, URL, or identifier, not a machine-specific absolute path."
}
```