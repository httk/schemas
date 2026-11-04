# Number of atoms (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/structure/natoms`](https://schemas.httk.org/defs/v0.1/properties/structure/natoms.md)**  
**Definition name:** `natoms`

**Property name:** Number of atoms  
**Description:** The number of atoms in the cell spanned by `lattice_vectors` (the full cell, also when `site_coordinate_span` lists only an asymmetric unit or fundamental domain).
Defined only for ordered structures, where every site is fully occupied by exactly one chemical species (no vacancies, mixed occupancy or implicit atoms); for such a structure with `site_coordinate_span` `unit_cell` it equals `nsites`.
A null value means the structure is disordered or the count is not available.
This is the reference count for properties whose `x-httk-normalization` names `_httk_natoms`.  
**Type:** integer  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** Support for queries on this property is OPTIONAL.  



**Examples:**



**Formats:** [[JSON](natoms.json)] [[MD](natoms.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/structure/natoms",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Number of atoms",
    "x-optimade-type": "integer",
    "x-optimade-unit": "dimensionless",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "natoms",
        "label": "natoms_structure_httk"
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
    "description": "The number of atoms in the cell spanned by `lattice_vectors` (the full cell, also when `site_coordinate_span` lists only an asymmetric unit or fundamental domain).\nDefined only for ordered structures, where every site is fully occupied by exactly one chemical species (no vacancies, mixed occupancy or implicit atoms); for such a structure with `site_coordinate_span` `unit_cell` it equals `nsites`.\nA null value means the structure is disordered or the count is not available.\nThis is the reference count for properties whose `x-httk-normalization` names `_httk_natoms`."
}
```