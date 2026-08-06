# Species constituent charges (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/chemistry/species_charges`](https://schemas.httk.org/defs/v0.1/properties/chemistry/species_charges.md)**  
**Definition name:** `species_charges`

**Property name:** Species constituent charges  
**Description:** The explicitly assigned charge of each constituent of a species, as a dimensionless charge number, i.e., the charge in units of the elementary charge.  
**Type:** list  

This property appears as a key inside each dictionary of the `species` property of a structure, alongside `chemical_symbols` and `concentration`.
A typical source of these values is a formal oxidation state assigned to a decorated species, such as the `2` of `Fe2+`.

**Requirements/Conventions**:

- The list MUST have the same length and order as the `chemical_symbols` list of the species dictionary it appears in.
- Each entry is the assigned charge number of the corresponding constituent.
- An entry MUST be `null` where no charge is assigned to that constituent.
- The value MUST only state charges explicitly assigned by the data source.
  It MUST NOT be derived, e.g., by charge balancing or by inference from the composition.
- The value MUST be `null`, or the key omitted, where no constituent has an assigned charge.
- An explicit charge of `0` differs from `null`: `0` states that the constituent is assigned as neutral, while `null` states nothing.

**Examples:**

- `[2.0]`
- `[3.0, null]`
- `[null, null]`

**Formats:** [[JSON](species_charges.json)] [[MD](species_charges.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/chemistry/species_charges",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Species constituent charges",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "species_charges",
        "label": "species_charges_chemistry"
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
    "description": "The explicitly assigned charge of each constituent of a species, as a dimensionless charge number, i.e., the charge in units of the elementary charge.\n\nThis property appears as a key inside each dictionary of the `species` property of a structure, alongside `chemical_symbols` and `concentration`.\nA typical source of these values is a formal oxidation state assigned to a decorated species, such as the `2` of `Fe2+`.\n\n**Requirements/Conventions**:\n\n- The list MUST have the same length and order as the `chemical_symbols` list of the species dictionary it appears in.\n- Each entry is the assigned charge number of the corresponding constituent.\n- An entry MUST be `null` where no charge is assigned to that constituent.\n- The value MUST only state charges explicitly assigned by the data source.\n  It MUST NOT be derived, e.g., by charge balancing or by inference from the composition.\n- The value MUST be `null`, or the key omitted, where no constituent has an assigned charge.\n- An explicit charge of `0` differs from `null`: `0` states that the constituent is assigned as neutral, while `null` states nothing.",
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
            2.0
        ],
        [
            3.0,
            null
        ],
        [
            null,
            null
        ]
    ]
}
```