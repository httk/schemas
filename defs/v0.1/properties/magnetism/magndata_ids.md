# MAGNDATA identifiers (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/magnetism/magndata_ids`](https://schemas.httk.org/defs/v0.1/properties/magnetism/magndata_ids.md)**  
**Definition name:** `magndata_ids`

**Property name:** MAGNDATA identifiers  
**Description:** The identifiers of MAGNDATA magnetic-structure entries associated with a material.  
**Type:** list  

Each item is an opaque MAGNDATA identifier string (for example `0.379`) as used by the MAGNDATA database at the Bilbao Crystallographic Server.
A null value means no MAGNDATA identifiers are recorded for this material; an empty list is not used.

**Examples:**

- `["0.379"]`
- `["0.296", "0.295"]`

**Formats:** [[JSON](magndata_ids.json)] [[MD](magndata_ids.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/magnetism/magndata_ids",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "MAGNDATA identifiers",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "magndata_ids",
        "label": "magndata_ids_magnetism"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "array",
        "null"
    ],
    "items": {
        "x-optimade-type": "string",
        "x-optimade-unit": "inapplicable",
        "type": [
            "string"
        ]
    },
    "description": "The identifiers of MAGNDATA magnetic-structure entries associated with a material.\n\nEach item is an opaque MAGNDATA identifier string (for example `0.379`) as used by the MAGNDATA database at the Bilbao Crystallographic Server.\nA null value means no MAGNDATA identifiers are recorded for this material; an empty list is not used.",
    "examples": [
        [
            "0.379"
        ],
        [
            "0.296",
            "0.295"
        ]
    ]
}
```