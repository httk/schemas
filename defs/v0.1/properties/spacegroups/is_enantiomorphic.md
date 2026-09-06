# is enantiomorphic (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_enantiomorphic`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_enantiomorphic.md)**  
**Definition name:** `is_enantiomorphic`

**Property name:** is enantiomorphic  
**Description:** Boolean flag indicating whether the space-group type belongs to an enantiomorphic pair.  
**Type:** boolean  

This identifies the 22 space-group types belonging to 11 pairs of distinct enantiomorphic types.
The partner IT number is given by `it_number_enantiomorphic`; membership is more restrictive than the Sohncke-group flag `is_chiral`.

**Examples:**

- `false`
- `true`

**Formats:** [[JSON](is_enantiomorphic.json)] [[MD](is_enantiomorphic.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_enantiomorphic",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "is enantiomorphic",
    "x-optimade-type": "boolean",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "is_enantiomorphic",
        "label": "is_enantiomorphic_spacegroups"
    },
    "type": [
        "boolean",
        "null"
    ],
    "description": "Boolean flag indicating whether the space-group type belongs to an enantiomorphic pair.\n\nThis identifies the 22 space-group types belonging to 11 pairs of distinct enantiomorphic types.\nThe partner IT number is given by `it_number_enantiomorphic`; membership is more restrictive than the Sohncke-group flag `is_chiral`.",
    "x-optimade-unit": "inapplicable",
    "examples": [
        false,
        true
    ]
}
```