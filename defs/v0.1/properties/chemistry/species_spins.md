# Species constituent spins (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/chemistry/species_spins`](https://schemas.httk.org/defs/v0.1/properties/chemistry/species_spins.md)**  
**Definition name:** `species_spins`

**Property name:** Species constituent spins  
**Description:** The idealized spin assigned to each constituent of a species, as a dimensionless signed number.  
**Type:** list  

This property appears as a key inside each dictionary of the `species` property of a structure, alongside `chemical_symbols` and `concentration`.
It states an idealized attribute of the species assignment itself, such as a nominal high-spin or low-spin state, with sign giving the direction relative to a collinear axis chosen by the source.
It is distinct from a calculated or measured magnetic moment of a site; see the structure-level property [`site_moments`](https://schemas.httk.org/defs/v0.1/properties/magnetism/site_moments) for those.

**Requirements/Conventions**:

- The list MUST have the same length and order as the `chemical_symbols` list of the species dictionary it appears in.
- Each entry is the idealized spin assigned to the corresponding constituent.
- An entry MUST be `null` where no spin is assigned to that constituent.
- The value MUST only state spins explicitly assigned by the data source.
- The value MUST be `null`, or the key omitted, where no constituent has an assigned spin.
- An explicit spin of `0` differs from `null`: `0` states that the constituent is assigned as spin-free, while `null` states nothing.

**Examples:**

- `[5.0]`
- `[-4.0, null]`

**Formats:** [[JSON](species_spins.json)] [[MD](species_spins.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/chemistry/species_spins",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Species constituent spins",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "species_spins",
        "label": "species_spins_chemistry"
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
    "description": "The idealized spin assigned to each constituent of a species, as a dimensionless signed number.\n\nThis property appears as a key inside each dictionary of the `species` property of a structure, alongside `chemical_symbols` and `concentration`.\nIt states an idealized attribute of the species assignment itself, such as a nominal high-spin or low-spin state, with sign giving the direction relative to a collinear axis chosen by the source.\nIt is distinct from a calculated or measured magnetic moment of a site; see the structure-level property [`site_moments`](https://schemas.httk.org/defs/v0.1/properties/magnetism/site_moments) for those.\n\n**Requirements/Conventions**:\n\n- The list MUST have the same length and order as the `chemical_symbols` list of the species dictionary it appears in.\n- Each entry is the idealized spin assigned to the corresponding constituent.\n- An entry MUST be `null` where no spin is assigned to that constituent.\n- The value MUST only state spins explicitly assigned by the data source.\n- The value MUST be `null`, or the key omitted, where no constituent has an assigned spin.\n- An explicit spin of `0` differs from `null`: `0` states that the constituent is assigned as spin-free, while `null` states nothing.",
    "items": {
        "x-optimade-type": "float",
        "x-optimade-unit": "dimensionless",
        "type": [
            "number",
            "null"
        ]
    },
    "examples": [
        [
            5.0
        ],
        [
            -4.0,
            null
        ]
    ]
}
```