# is chiral (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_chiral`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_chiral.md)**  
**Definition name:** `is_chiral`

**Property name:** is chiral  
**Description:** Whether every operation of the space group preserves handedness, i.e. every linear part has determinant +1.
This is cctbx's `is_chiral()` convention and identifies the 65 Sohncke space-group types, excluding mirrors, inversion, glide reflections, and rotoinversions.
It does not mean that the space-group type belongs to one of the 11 enantiomorphic pairs; that is recorded by `is_enantiomorphic`.
It does not by itself determine the handedness or chirality of a molecular motif.  
**Type:** boolean  



**Examples:**

- `true`
- `false`

**Formats:** [[JSON](is_chiral.json)] [[MD](is_chiral.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_chiral",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "is chiral",
    "x-optimade-type": "boolean",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "is_chiral",
        "label": "is_chiral_spacegroups"
    },
    "type": [
        "boolean",
        "null"
    ],
    "description": "Whether every operation of the space group preserves handedness, i.e. every linear part has determinant +1.\nThis is cctbx's `is_chiral()` convention and identifies the 65 Sohncke space-group types, excluding mirrors, inversion, glide reflections, and rotoinversions.\nIt does not mean that the space-group type belongs to one of the 11 enantiomorphic pairs; that is recorded by `is_enantiomorphic`.\nIt does not by itself determine the handedness or chirality of a molecular motif.",
    "x-optimade-unit": "inapplicable",
    "examples": [
        true,
        false
    ]
}
```