# Criterion target (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/transformations/target`](https://schemas.httk.org/defs/v0.1/properties/transformations/target.md)**  
**Definition name:** `target`

**Property name:** Criterion target  
**Description:** Exact right-hand side of a generated modular linear criterion, stored as a list of fraction strings.  
**Type:** list  

This field appears in `criteria` items of basis-transform records, for example in backward-lift criteria.
The current generator emits one scalar equation per record, so `target` has one component and the condition is `sum_i dot(coeffs[i][0], q_i) = target[0] (mod 1)`.
The target component is normalized to [0,1); zero denotes an integer-valued left-hand side, not necessarily the real number zero.
The role-coordinate and coefficient conventions are specified in `/defs/v0.1/properties/symmetry/basis_transform`.

**Examples:**

- `["0"]`
- `["1/2"]`

**Formats:** [[JSON](target.json)] [[MD](target.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/target",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Criterion target",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "target",
        "label": "target_transformations"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "array",
        "null"
    ],
    "description": "Exact right-hand side of a generated modular linear criterion, stored as a list of fraction strings.\n\nThis field appears in `criteria` items of basis-transform records, for example in backward-lift criteria.\nThe current generator emits one scalar equation per record, so `target` has one component and the condition is `sum_i dot(coeffs[i][0], q_i) = target[0] (mod 1)`.\nThe target component is normalized to [0,1); zero denotes an integer-valued left-hand side, not necessarily the real number zero.\nThe role-coordinate and coefficient conventions are specified in `/defs/v0.1/properties/symmetry/basis_transform`.",
    "items": {
        "$id": "https://schemas.httk.org/defs/v0.1/properties/core/fraction",
        "title": "Fraction",
        "x-optimade-type": "string",
        "x-optimade-definition": {
            "label": "fraction_core",
            "kind": "property",
            "version": "0.1.0",
            "format": "1.3",
            "name": "fraction"
        },
        "type": [
            "string",
            "null"
        ],
        "description": "A numerical representation formed as the quotient of two numbers represented as a string.",
        "examples": [
            "2/3",
            "5/42",
            "10",
            "0"
        ],
        "x-optimade-unit": "inapplicable"
    },
    "examples": [
        [
            "0"
        ],
        [
            "1/2"
        ]
    ]
}
```