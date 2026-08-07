# Magnetic space group (BNS) (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/magnetism/magnetic_space_group_bns`](https://schemas.httk.org/defs/v0.1/properties/magnetism/magnetic_space_group_bns.md)**  
**Definition name:** `magnetic_space_group_bns`

**Property name:** Magnetic space group (BNS)  
**Description:** The magnetic space group of a material in Belov-Neronova-Smirnova (BNS) notation.  
**Type:** string  

The value combines the BNS Hermann-Mauguin symbol with its BNS number in parentheses, for example `Pn'm'a (62.446)`. Primes are rendered as apostrophes, and an overbar is rendered as a leading minus sign.
A null value means no BNS symbol is available or recorded for this material.

**Examples:**

- `"Pn'm'a (62.446)"`
- `"R-3c' (167.107)"`

**Formats:** [[JSON](magnetic_space_group_bns.json)] [[MD](magnetic_space_group_bns.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/magnetism/magnetic_space_group_bns",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Magnetic space group (BNS)",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "magnetic_space_group_bns",
        "label": "magnetic_space_group_bns_magnetism"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "string",
        "null"
    ],
    "description": "The magnetic space group of a material in Belov-Neronova-Smirnova (BNS) notation.\n\nThe value combines the BNS Hermann-Mauguin symbol with its BNS number in parentheses, for example `Pn'm'a (62.446)`. Primes are rendered as apostrophes, and an overbar is rendered as a leading minus sign.\nA null value means no BNS symbol is available or recorded for this material.",
    "examples": [
        "Pn'm'a (62.446)",
        "R-3c' (167.107)"
    ]
}
```