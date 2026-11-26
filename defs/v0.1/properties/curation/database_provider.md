# external database provider (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/curation/database_provider`](https://schemas.httk.org/defs/v0.1/properties/curation/database_provider.md)**  
**Definition name:** `database_provider`

**Property name:** external database provider  
**Description:** The provider of the external database. This is the OPTIMADE provider prefix, as registered in the OPTIMADE providers list, e.g. "cod", "oqmd", or "mp", and an equivalent short lowercase name when no registered prefix exists.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](database_provider.json)] [[MD](database_provider.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/database_provider",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "external database provider",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "database_provider",
        "label": "database_provider_property_httk"
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
    "description": "The provider of the external database. This is the OPTIMADE provider prefix, as registered in the OPTIMADE providers list, e.g. \"cod\", \"oqmd\", or \"mp\", and an equivalent short lowercase name when no registered prefix exists."
}
```