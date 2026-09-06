# is centric (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_centric`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_centric.md)**  
**Definition name:** `is_centric`

**Property name:** is centric  
**Description:** Whether the space group contains an inversion operation `(W,w)` with `W = -I`.
The inversion center need not be the coordinate origin; one such center is at `w/2` in fractional coordinates.
This tests the space-group symmetry, not the centricity of an individual diffraction reflection.  
**Type:** boolean  



**Examples:**

- `false`
- `true`

**Formats:** [[JSON](is_centric.json)] [[MD](is_centric.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_centric",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "is centric",
    "x-optimade-type": "boolean",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "is_centric",
        "label": "is_centric_spacegroups"
    },
    "type": [
        "boolean",
        "null"
    ],
    "description": "Whether the space group contains an inversion operation `(W,w)` with `W = -I`.\nThe inversion center need not be the coordinate origin; one such center is at `w/2` in fractional coordinates.\nThis tests the space-group symmetry, not the centricity of an individual diffraction reflection.",
    "x-optimade-unit": "inapplicable",
    "examples": [
        false,
        true
    ]
}
```