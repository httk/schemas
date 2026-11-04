# Number of formula units (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/structure/nformula_units`](https://schemas.httk.org/defs/v0.1/properties/structure/nformula_units.md)**  
**Definition name:** `nformula_units`

**Property name:** Number of formula units  
**Description:** The number of formula units in the cell the entry describes: `_httk_natoms` divided by the number of atoms in one formula unit of `chemical_formula_reduced`.
This is not the crystallographic Z, which counts the formula as written per conventional cell.
A null value whenever `_httk_natoms` is null.  
**Type:** integer  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** Support for queries on this property is OPTIONAL.  



**Examples:**



**Formats:** [[JSON](nformula_units.json)] [[MD](nformula_units.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/structure/nformula_units",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Number of formula units",
    "x-optimade-type": "integer",
    "x-optimade-unit": "dimensionless",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "nformula_units",
        "label": "nformula_units_structure_httk"
    },
    "x-optimade-requirements": {
        "support": "may",
        "sortable": false,
        "query-support": "none"
    },
    "type": [
        "integer",
        "null"
    ],
    "description": "The number of formula units in the cell the entry describes: `_httk_natoms` divided by the number of atoms in one formula unit of `chemical_formula_reduced`.\nThis is not the crystallographic Z, which counts the formula as written per conventional cell.\nA null value whenever `_httk_natoms` is null."
}
```