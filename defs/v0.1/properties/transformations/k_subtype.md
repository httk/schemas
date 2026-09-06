# Klassengleiche subgroup subtype (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/transformations/k_subtype`](https://schemas.httk.org/defs/v0.1/properties/transformations/k_subtype.md)**  
**Definition name:** `k_subtype`

**Property name:** Klassengleiche subgroup subtype  
**Description:** Subtype of a klassengleiche (`k`) subgroup relation.  
**Type:** string  

The value distinguishes loss of centering translations from enlarged-unit-cell subgroups.
The value is null for non-`k` relations and for records that are not subgroup relations.

For the emitted embedding convention `x_G = P*x_H + p`, `loss_of_centering_translation` is assigned when `abs(det(P)) = 1` and the subgroup cell has fewer centering translations than the parent cell.
Other klassengleiche embeddings are assigned `enlarged_unit_cell`.
The subtype is therefore a convention tied to the recorded cells, not an invariant of the abstract pair of group types; a cell change can combine translation loss with a change of centering description.

**Examples:**

- `"enlarged_unit_cell"`
- `"loss_of_centering_translation"`

**Formats:** [[JSON](k_subtype.json)] [[MD](k_subtype.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/k_subtype",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Klassengleiche subgroup subtype",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "k_subtype",
        "label": "k_subtype_transformations"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "Subtype of a klassengleiche (`k`) subgroup relation.\n\nThe value distinguishes loss of centering translations from enlarged-unit-cell subgroups.\nThe value is null for non-`k` relations and for records that are not subgroup relations.\n\nFor the emitted embedding convention `x_G = P*x_H + p`, `loss_of_centering_translation` is assigned when `abs(det(P)) = 1` and the subgroup cell has fewer centering translations than the parent cell.\nOther klassengleiche embeddings are assigned `enlarged_unit_cell`.\nThe subtype is therefore a convention tied to the recorded cells, not an invariant of the abstract pair of group types; a cell change can combine translation loss with a change of centering description.",
    "x-optimade-unit": "inapplicable",
    "enum": [
        "loss_of_centering_translation",
        "enlarged_unit_cell",
        null
    ],
    "examples": [
        "enlarged_unit_cell",
        "loss_of_centering_translation"
    ]
}
```