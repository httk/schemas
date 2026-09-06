# Bravais type (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/bravais_type`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/bravais_type.md)**  
**Definition name:** `bravais_type`

**Property name:** Bravais type  
**Description:** The Bravais type of the translational lattice.  
**Type:** string  

The symbol consists of a lower-case crystal-family letter followed by an upper-case centring symbol.
Side-centred settings (`A`, `B`, or `C` centring) are normalized to the setting-independent `S` symbol for monoclinic and orthorhombic lattices.
Body-centred monoclinic settings keep the symbol `mI`, which describes the same lattice type as `mS` in a different conventional cell choice.

The first character follows the crystal-family notation: `a` denotes triclinic (anorthic), and `h` covers the hexagonal family, which includes trigonal and hexagonal crystal systems.
Rhombohedral lattices have `hR` in both hexagonal-axis and primitive rhombohedral-axis descriptions; `centring_type: P` in rhombohedral axes does not imply `hP`.
The retained `mI` alternative means the vocabulary has 15 symbols for 14 Bravais lattice types.

**Examples:**

- `"aP"`
- `"mS"`

**Formats:** [[JSON](bravais_type.json)] [[MD](bravais_type.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/bravais_type",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Bravais type",
    "x-optimade-type": "string",
    "x-compatibility": [
        "https://www.iucr.org/__data/iucr/cifdic_html/2/cif_sym.dic/Ispace_group.Bravais_type.html"
    ],
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "bravais_type",
        "label": "bravais_type_spacegroups"
    },
    "type": [
        "string",
        "null"
    ],
    "description": "The Bravais type of the translational lattice.\n\nThe symbol consists of a lower-case crystal-family letter followed by an upper-case centring symbol.\nSide-centred settings (`A`, `B`, or `C` centring) are normalized to the setting-independent `S` symbol for monoclinic and orthorhombic lattices.\nBody-centred monoclinic settings keep the symbol `mI`, which describes the same lattice type as `mS` in a different conventional cell choice.\n\nThe first character follows the crystal-family notation: `a` denotes triclinic (anorthic), and `h` covers the hexagonal family, which includes trigonal and hexagonal crystal systems.\nRhombohedral lattices have `hR` in both hexagonal-axis and primitive rhombohedral-axis descriptions; `centring_type: P` in rhombohedral axes does not imply `hP`.\nThe retained `mI` alternative means the vocabulary has 15 symbols for 14 Bravais lattice types.",
    "x-optimade-unit": "inapplicable",
    "enum": [
        "aP",
        "mP",
        "mS",
        "mI",
        "oP",
        "oS",
        "oF",
        "oI",
        "tP",
        "tI",
        "hP",
        "hR",
        "cP",
        "cI",
        "cF",
        null
    ],
    "examples": [
        "aP",
        "mS"
    ]
}
```