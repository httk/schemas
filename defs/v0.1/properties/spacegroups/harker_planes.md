# Harker planes (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/harker_planes`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/harker_planes.md)**  
**Definition name:** `harker_planes`

**Property name:** Harker planes  
**Description:** Harker planes of the space group in fractional Patterson coordinates.  
**Type:** list  

Each entry describes one plane or special-position condition with an expression and optional exact normal, point, and constant data.

A Harker plane contains Patterson displacement vectors between symmetry-related sites.
For a contributing operation `(W,w)`, those displacements are parameterized by `(W-I)*x+w`; the algebraic rendering may reverse parameter signs without changing the plane.
The current generator emits the cctbx plane descriptors `algebraic`, `normal`, and `point`; the optional `xyz` and `const` fields are retained but are not emitted.
Here `normal` is the direct-lattice direction returned by cctbx for the rotation axis, and `point` is a fractional point on the plane.
For lattice metric g, a displacement u lies in that plane when `normal^T*g*(u-point) = 0`; the fractional components of `normal` must not be treated as a Cartesian unit normal or a reciprocal covector.
The list covers planes constructed by cctbx's Harker-plane routine; it is not an enumeration of all Patterson peaks, Harker lines, or special points.

**Examples:**

- `[{"algebraic": "2*x,0,2*z", "normal": [0, 1, 0], "point": ["0", "0", "0"]}]`

**Formats:** [[JSON](harker_planes.json)] [[MD](harker_planes.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/harker_planes",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Harker planes",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "harker_planes",
        "label": "harker_planes_spacegroups"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "array",
        "null"
    ],
    "description": "Harker planes of the space group in fractional Patterson coordinates.\n\nEach entry describes one plane or special-position condition with an expression and optional exact normal, point, and constant data.\n\nA Harker plane contains Patterson displacement vectors between symmetry-related sites.\nFor a contributing operation `(W,w)`, those displacements are parameterized by `(W-I)*x+w`; the algebraic rendering may reverse parameter signs without changing the plane.\nThe current generator emits the cctbx plane descriptors `algebraic`, `normal`, and `point`; the optional `xyz` and `const` fields are retained but are not emitted.\nHere `normal` is the direct-lattice direction returned by cctbx for the rotation axis, and `point` is a fractional point on the plane.\nFor lattice metric g, a displacement u lies in that plane when `normal^T*g*(u-point) = 0`; the fractional components of `normal` must not be treated as a Cartesian unit normal or a reciprocal covector.\nThe list covers planes constructed by cctbx's Harker-plane routine; it is not an enumeration of all Patterson peaks, Harker lines, or special points.",
    "items": {
        "x-optimade-type": "dictionary",
        "x-optimade-unit": "inapplicable",
        "type": [
            "object",
            "null"
        ],
        "description": "One Harker plane or special-position condition.",
        "properties": {
            "algebraic": {
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "string",
                    "null"
                ],
                "description": "Algebraic expression for the condition when emitted by cctbx."
            },
            "xyz": {
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "string",
                    "null"
                ],
                "description": "Optional plane expression in `x,y,z` notation; not emitted by the current generator."
            },
            "normal": {
                "x-optimade-type": "list",
                "x-optimade-unit": "inapplicable",
                "x-optimade-dimensions": {
                    "names": [
                        "dim_lattice"
                    ],
                    "sizes": [
                        3
                    ]
                },
                "type": [
                    "array",
                    "null"
                ],
                "description": "Integer direct-lattice direction normal to the plane in the physical metric, following cctbx's rotation-axis convention.",
                "items": {
                    "x-optimade-type": "integer",
                    "x-optimade-unit": "inapplicable",
                    "type": [
                        "integer"
                    ],
                    "description": "One integer component of the normal vector."
                }
            },
            "point": {
                "x-optimade-type": "list",
                "x-optimade-unit": "inapplicable",
                "x-optimade-dimensions": {
                    "names": [
                        "dim_lattice"
                    ],
                    "sizes": [
                        3
                    ]
                },
                "type": [
                    "array",
                    "null"
                ],
                "description": "Point on the plane.",
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
                }
            },
            "const": {
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
            }
        }
    },
    "examples": [
        [
            {
                "algebraic": "2*x,0,2*z",
                "normal": [
                    0,
                    1,
                    0
                ],
                "point": [
                    "0",
                    "0",
                    "0"
                ]
            }
        ]
    ]
}
```