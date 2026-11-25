# import source item (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/source_item`](https://schemas.httk.org/defs/v0.1/properties/imports/source_item.md)**  
**Definition name:** `source_item`

**Property name:** import source item  
**Description:** The item within the source when the source holds several, e.g. a CIF data block name; null when the source holds one item.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](source_item.json)] [[MD](source_item.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/source_item",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import source item",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "source_item",
        "label": "source_item_property_httk"
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
    "description": "The item within the source when the source holds several, e.g. a CIF data block name; null when the source holds one item."
}
```