# external database (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/curation/database`](https://schemas.httk.org/defs/v0.1/properties/curation/database.md)**  
**Definition name:** `database`

**Property name:** external database  
**Description:** The external database. This is the OPTIMADE provider prefix, as registered in the OPTIMADE providers list, when that prefix is enough to distinguish entry ids, e.g. "cod", "oqmd", or "mp"; "<prefix>:<short database id>" when one provider has several databases; and an equivalent short lowercase name when no registered prefix exists.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](database.json)] [[MD](database.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/database",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "external database",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "database",
        "label": "database_property_httk"
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
    "description": "The external database. This is the OPTIMADE provider prefix, as registered in the OPTIMADE providers list, when that prefix is enough to distinguish entry ids, e.g. \"cod\", \"oqmd\", or \"mp\"; \"<prefix>:<short database id>\" when one provider has several databases; and an equivalent short lowercase name when no registered prefix exists."
}
```