# Maximal subgroup type (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/transformations/subgroup_type`](https://schemas.httk.org/defs/v0.1/properties/transformations/subgroup_type.md)**  
**Definition name:** `subgroup_type`

**Property name:** Maximal subgroup type  
**Description:** International Tables maximal subgroup class.  
**Type:** string  

The value is `t` for a translationengleiche subgroup and `k` for a klassengleiche subgroup.
The field is omitted when the enclosing record is not a maximal subgroup relation.

A translationengleiche subgroup retains the complete translation lattice and loses point symmetry: `i_T = 1`, `i_P > 1`.
A klassengleiche subgroup retains the point group and loses translations: `i_P = 1`, `i_T > 1`.
For a maximal proper subgroup these are the alternatives; a subgroup losing both is not represented by either value.
The underlying t/k classification describes what symmetry is lost and does not by itself prove that an embedding is maximal.

**Examples:**

- `"k"`
- `"t"`

**Formats:** [[JSON](subgroup_type.json)] [[MD](subgroup_type.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/subgroup_type",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Maximal subgroup type",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "subgroup_type",
        "label": "subgroup_type_transformations"
    },
    "type": [
        "string"
    ],
    "description": "International Tables maximal subgroup class.\n\nThe value is `t` for a translationengleiche subgroup and `k` for a klassengleiche subgroup.\nThe field is omitted when the enclosing record is not a maximal subgroup relation.\n\nA translationengleiche subgroup retains the complete translation lattice and loses point symmetry: `i_T = 1`, `i_P > 1`.\nA klassengleiche subgroup retains the point group and loses translations: `i_P = 1`, `i_T > 1`.\nFor a maximal proper subgroup these are the alternatives; a subgroup losing both is not represented by either value.\nThe underlying t/k classification describes what symmetry is lost and does not by itself prove that an embedding is maximal.",
    "enum": [
        "t",
        "k"
    ],
    "x-optimade-unit": "inapplicable",
    "examples": [
        "k",
        "t"
    ]
}
```