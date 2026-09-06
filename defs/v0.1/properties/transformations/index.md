# Subgroup or transform index (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/transformations/index`](https://schemas.httk.org/defs/v0.1/properties/transformations/index.md)**  
**Definition name:** `index`

**Property name:** Subgroup or transform index  
**Description:** Subgroup or transform index.  
**Type:** integer  

For subgroup transforms it is the crystallographic subgroup index `[G:H]`, equal to the determinant factor of the basis transformation when applicable.

For the column-vector convention `x_G = P*x_H + p`, the exact index formula is `[G:H] = abs(det(P)) * n_symops(G) / n_symops(H)`.
Equivalently it is the product of the translation index `i_T = abs(det(P))*n_centering_translations(G)/n_centering_translations(H)` and the point-group index `i_P = n_pointgroup_symops(G)/n_pointgroup_symops(H)`.
Thus a point-symmetry reduction can have index greater than one even when `det(P) = 1`.
In `hall_to_it_std_transform` the value is one even if the two cell conventions have different volumes; an ordinal index in another table must be interpreted as documented by that parent property.

**Examples:**

- `2`
- `4`

**Formats:** [[JSON](index.json)] [[MD](index.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/index",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Subgroup or transform index",
    "x-optimade-type": "integer",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "index",
        "label": "index_transformations"
    },
    "type": [
        "integer",
        "null"
    ],
    "description": "Subgroup or transform index.\n\nFor subgroup transforms it is the crystallographic subgroup index `[G:H]`, equal to the determinant factor of the basis transformation when applicable.\n\nFor the column-vector convention `x_G = P*x_H + p`, the exact index formula is `[G:H] = abs(det(P)) * n_symops(G) / n_symops(H)`.\nEquivalently it is the product of the translation index `i_T = abs(det(P))*n_centering_translations(G)/n_centering_translations(H)` and the point-group index `i_P = n_pointgroup_symops(G)/n_pointgroup_symops(H)`.\nThus a point-symmetry reduction can have index greater than one even when `det(P) = 1`.\nIn `hall_to_it_std_transform` the value is one even if the two cell conventions have different volumes; an ordinal index in another table must be interpreted as documented by that parent property.",
    "x-optimade-unit": "inapplicable",
    "examples": [
        2,
        4
    ]
}
```