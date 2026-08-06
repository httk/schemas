# Frame stresses (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_stresses`](https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_stresses.md)**  
**Definition name:** `frame_stresses`

**Property name:** Frame stresses  
**Description:** The stress tensor of each frame of a trajectory, aligned with the trajectory frame axis (`dim_frames`).
Each tensor is given in Voigt order [xx, yy, zz, yz, xz, xy], with tensile stress positive, in gigapascal (GPa; 1 GPa = 10^9 Pa).
A `null` value indicates that the stress tensor of the corresponding frame is unknown.  
**Type:** list  



**Examples:**



**Formats:** [[JSON](frame_stresses.json)] [[MD](frame_stresses.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/trajectories/frame_stresses",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Frame stresses",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "frame_stresses",
        "label": "frame_stresses_trajectories_httk"
    },
    "x-optimade-unit": "GPa",
    "x-optimade-unit-definitions": [
        {
            "$id": "https://schemas.httk.org/defs/v0.1/units/si/general/gigapascal",
            "title": "gigapascal",
            "symbol": "GPa",
            "display-symbol": "GPa",
            "description": "A unit of pressure and stress equal to 10^9 pascals.",
            "x-optimade-definition": {
                "label": "gigapascal_si_general",
                "kind": "unit",
                "format": "1.2",
                "version": "0.1.0",
                "name": "gigapascal"
            }
        }
    ],
    "x-optimade-dimensions": {
        "names": [
            "dim_frames"
        ],
        "sizes": [
            null
        ]
    },
    "type": [
        "array",
        "null"
    ],
    "items": {
        "x-optimade-type": "list",
        "x-optimade-unit": "inapplicable",
        "x-optimade-dimensions": {
            "names": [
                "dim_voigt"
            ],
            "sizes": [
                6
            ]
        },
        "type": [
            "array",
            "null"
        ],
        "items": {
            "x-optimade-type": "float",
            "x-optimade-unit": "GPa",
            "type": [
                "number"
            ]
        }
    },
    "description": "The stress tensor of each frame of a trajectory, aligned with the trajectory frame axis (`dim_frames`).\nEach tensor is given in Voigt order [xx, yy, zz, yz, xz, xy], with tensile stress positive, in gigapascal (GPa; 1 GPa = 10^9 Pa).\nA `null` value indicates that the stress tensor of the corresponding frame is unknown."
}
```