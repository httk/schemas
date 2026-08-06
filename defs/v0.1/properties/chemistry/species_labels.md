# Species constituent labels (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/chemistry/species_labels`](https://schemas.httk.org/defs/v0.1/properties/chemistry/species_labels.md)**  
**Definition name:** `species_labels`

**Property name:** Species constituent labels  
**Description:** A free-form label attached to each constituent of a species.  
**Type:** list  

This property appears as a key inside each dictionary of the `species` property of a structure, alongside `chemical_symbols` and `concentration`.
A label distinguishes constituents that are otherwise identically described, and carries source-specific naming such as the name of a placeholder species assigned to the non-chemical symbol `"X"`.

**Requirements/Conventions**:

- The list MUST have the same length and order as the `chemical_symbols` list of the species dictionary it appears in.
- Each entry is the label of the corresponding constituent.
- An entry MUST be `null` where the corresponding constituent has no label.
- The value MUST be `null`, or the key omitted, where no constituent has a label.

**Examples:**

- `["water"]`
- `[null, "up"]`

**Formats:** [[JSON](species_labels.json)] [[MD](species_labels.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/chemistry/species_labels",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Species constituent labels",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "species_labels",
        "label": "species_labels_chemistry"
    },
    "x-optimade-unit": "inapplicable",
    "x-optimade-dimensions": {
        "names": [
            "dim_species_chemical_symbols"
        ],
        "sizes": [
            null
        ]
    },
    "type": [
        "array",
        "null"
    ],
    "description": "A free-form label attached to each constituent of a species.\n\nThis property appears as a key inside each dictionary of the `species` property of a structure, alongside `chemical_symbols` and `concentration`.\nA label distinguishes constituents that are otherwise identically described, and carries source-specific naming such as the name of a placeholder species assigned to the non-chemical symbol `\"X\"`.\n\n**Requirements/Conventions**:\n\n- The list MUST have the same length and order as the `chemical_symbols` list of the species dictionary it appears in.\n- Each entry is the label of the corresponding constituent.\n- An entry MUST be `null` where the corresponding constituent has no label.\n- The value MUST be `null`, or the key omitted, where no constituent has a label.",
    "items": {
        "x-optimade-type": "string",
        "x-optimade-unit": "inapplicable",
        "type": [
            "string",
            "null"
        ]
    },
    "examples": [
        [
            "water"
        ],
        [
            null,
            "up"
        ]
    ]
}
```