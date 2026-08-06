# Structure charge (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/chemistry/structure_charge`](https://schemas.httk.org/defs/v0.1/properties/chemistry/structure_charge.md)**  
**Definition name:** `structure_charge`

**Property name:** Structure charge  
**Description:** The explicitly assigned net charge of the whole structure, as a dimensionless charge number, i.e., the charge in units of the elementary charge.  
**Type:** float  

**Requirements/Conventions**:

- The value MUST only state a charge explicitly assigned to the structure by the data source.
  It MUST NOT be derived, e.g., by summing assigned constituent charges or oxidation states.
- The value refers to the content of the unit cell described by the structure entry.
- The value MUST be `null` where no charge is assigned.
- An explicit charge of `0` differs from `null`: `0` states that the structure is assigned as neutral, while `null` states nothing.

**Examples:**

- `0.0`
- `-2.0`
- `1.0`

**Formats:** [[JSON](structure_charge.json)] [[MD](structure_charge.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/chemistry/structure_charge",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Structure charge",
    "x-optimade-type": "float",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "structure_charge",
        "label": "structure_charge_chemistry"
    },
    "x-optimade-unit": "dimensionless",
    "type": [
        "number",
        "null"
    ],
    "description": "The explicitly assigned net charge of the whole structure, as a dimensionless charge number, i.e., the charge in units of the elementary charge.\n\n**Requirements/Conventions**:\n\n- The value MUST only state a charge explicitly assigned to the structure by the data source.\n  It MUST NOT be derived, e.g., by summing assigned constituent charges or oxidation states.\n- The value refers to the content of the unit cell described by the structure entry.\n- The value MUST be `null` where no charge is assigned.\n- An explicit charge of `0` differs from `null`: `0` states that the structure is assigned as neutral, while `null` states nothing.",
    "examples": [
        0.0,
        -2.0,
        1.0
    ]
}
```