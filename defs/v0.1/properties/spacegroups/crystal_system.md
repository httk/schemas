# Crystal system (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system.md)**  
**Definition name:** `crystal_system`

**Property name:** Crystal system  
**Description:** The crystal system of the space group or point group.  
**Type:** string  

Values use the conventional crystallographic system names.

This classifies the crystallographic point symmetry, not a measured set of lattice lengths and angles.
Trigonal groups remain trigonal whether described in hexagonal or rhombohedral axes; use `bravais_type` on a space-group record for the translational lattice type.
Null denotes unavailable classification, not an additional crystal system.

**Examples:**

- `"triclinic"`
- `"monoclinic"`

**Formats:** [[JSON](crystal_system.json)] [[MD](crystal_system.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Crystal system",
    "x-optimade-type": "string",
    "x-compatibility": [
        "https://www.iucr.org/__data/iucr/cifdic_html/2/cif_sym.dic/Ispace_group.crystal_system.html"
    ],
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "crystal_system",
        "label": "crystal_system_pointgroups"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "The crystal system of the space group or point group.\n\nValues use the conventional crystallographic system names.\n\nThis classifies the crystallographic point symmetry, not a measured set of lattice lengths and angles.\nTrigonal groups remain trigonal whether described in hexagonal or rhombohedral axes; use `bravais_type` on a space-group record for the translational lattice type.\nNull denotes unavailable classification, not an additional crystal system.",
    "x-optimade-unit": "inapplicable",
    "enum": [
        "triclinic",
        "monoclinic",
        "orthorhombic",
        "tetragonal",
        "trigonal",
        "hexagonal",
        "cubic",
        null
    ],
    "examples": [
        "triclinic",
        "monoclinic"
    ]
}
```