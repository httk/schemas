# Wyckoff sets (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff_sets`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff_sets.md)**  
**Definition name:** `wyckoff_sets`

**Property name:** Wyckoff sets  
**Description:** Sets of Wyckoff letters related by normalizer operations.  
**Type:** list  

Each inner list groups Wyckoff positions that can be interchanged by the relevant normalizer action.

The generator forms these classes using the finite group obtained by expanding cctbx's additional Euclidean-normalizer generators in the recorded Hall setting.
Every Wyckoff letter occurs in exactly one inner list, including singleton lists.
A normalizer-induced permutation preserves multiplicity and the conjugacy type of site symmetry, although the oriented site-symmetry symbols can change.
This grouping describes the generated Euclidean-normalizer action; it is not a claim to enumerate equivalence under the full affine normalizer or its continuous freedoms.

**Examples:**

- `[["a"]]`
- `[["i"], ["h"], ["g"]]`

**Formats:** [[JSON](wyckoff_sets.json)] [[MD](wyckoff_sets.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/wyckoff_sets",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Wyckoff sets",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "wyckoff_sets",
        "label": "wyckoff_sets_spacegroups"
    },
    "type": [
        "array",
        "null"
    ],
    "description": "Sets of Wyckoff letters related by normalizer operations.\n\nEach inner list groups Wyckoff positions that can be interchanged by the relevant normalizer action.\n\nThe generator forms these classes using the finite group obtained by expanding cctbx's additional Euclidean-normalizer generators in the recorded Hall setting.\nEvery Wyckoff letter occurs in exactly one inner list, including singleton lists.\nA normalizer-induced permutation preserves multiplicity and the conjugacy type of site symmetry, although the oriented site-symmetry symbols can change.\nThis grouping describes the generated Euclidean-normalizer action; it is not a claim to enumerate equivalence under the full affine normalizer or its continuous freedoms.",
    "x-optimade-unit": "inapplicable",
    "items": {
        "x-optimade-type": "list",
        "type": [
            "array",
            "null"
        ],
        "description": "One Wyckoff-set combination.",
        "items": {
            "x-optimade-type": "string",
            "type": [
                "string",
                "null"
            ],
            "description": "Wyckoff letter.",
            "x-optimade-unit": "inapplicable"
        },
        "x-optimade-unit": "inapplicable"
    },
    "examples": [
        [
            [
                "a"
            ]
        ],
        [
            [
                "i"
            ],
            [
                "h"
            ],
            [
                "g"
            ]
        ]
    ]
}
```