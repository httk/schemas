# cctbx FFT grid factors (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/cctbx_fft_grid_factors`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/cctbx_fft_grid_factors.md)**  
**Definition name:** `cctbx_fft_grid_factors`

**Property name:** cctbx FFT grid factors  
**Description:** FFT grid-factor requirements derived from cctbx for the space group, its structure seminvariants, and its Euclidean normalizer.  
**Type:** dictionary  

Each value is a list of three positive integers, one per crystallographic axis, giving the factors that the corresponding FFT grid dimension must be divisible by for symmetry-adapted sampling.

**Requirements/Conventions**:

- It MUST be a dictionary with the following keys:

    - **space\_group**: REQUIRED; List of 3 Integers.
      Per-axis grid factors required by the space-group translations.

    - **seminvariant**: REQUIRED; List of 3 Integers.
      Per-axis grid factors required by the structure-seminvariant vectors and moduli.

    - **euclidean**: REQUIRED; List of 3 Integers.
      Per-axis grid factors obtained by refining the seminvariant factors against the Euclidean normalizer.

These factors impose divisibility constraints; they are not grid dimensions or a resolution prescription.
Choose grid dimensions as appropriate multiples and also enforce rotational compatibility, including relations between axes mixed by the symmetry.
Per-axis factors alone do not certify that an arbitrary three-dimensional grid is invariant under all rotations.
The `euclidean` factors are computed by refining the seminvariant gridding with the finite cctbx Euclidean-normalizer group in this same setting.

**Examples:**

- `{"space_group": [1, 1, 1], "seminvariant": [1, 1, 1], "euclidean": [1, 1, 1]}`
- `{"space_group": [1, 1, 1], "seminvariant": [2, 2, 2], "euclidean": [2, 2, 2]}`

**Formats:** [[JSON](cctbx_fft_grid_factors.json)] [[MD](cctbx_fft_grid_factors.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/cctbx_fft_grid_factors",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "cctbx FFT grid factors",
    "x-optimade-type": "dictionary",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "cctbx_fft_grid_factors",
        "label": "cctbx_fft_grid_factors_spacegroups"
    },
    "type": [
        "object",
        "null"
    ],
    "description": "FFT grid-factor requirements derived from cctbx for the space group, its structure seminvariants, and its Euclidean normalizer.\n\nEach value is a list of three positive integers, one per crystallographic axis, giving the factors that the corresponding FFT grid dimension must be divisible by for symmetry-adapted sampling.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **space\\_group**: REQUIRED; List of 3 Integers.\n      Per-axis grid factors required by the space-group translations.\n\n    - **seminvariant**: REQUIRED; List of 3 Integers.\n      Per-axis grid factors required by the structure-seminvariant vectors and moduli.\n\n    - **euclidean**: REQUIRED; List of 3 Integers.\n      Per-axis grid factors obtained by refining the seminvariant factors against the Euclidean normalizer.\n\nThese factors impose divisibility constraints; they are not grid dimensions or a resolution prescription.\nChoose grid dimensions as appropriate multiples and also enforce rotational compatibility, including relations between axes mixed by the symmetry.\nPer-axis factors alone do not certify that an arbitrary three-dimensional grid is invariant under all rotations.\nThe `euclidean` factors are computed by refining the seminvariant gridding with the finite cctbx Euclidean-normalizer group in this same setting.",
    "x-optimade-unit": "inapplicable",
    "properties": {
        "space_group": {
            "x-optimade-type": "list",
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
            "description": "FFT grid factors arising from the space-group translations.",
            "items": {
                "x-optimade-type": "integer",
                "type": [
                    "integer",
                    "null"
                ],
                "description": "One grid factor.",
                "x-optimade-unit": "inapplicable"
            },
            "x-optimade-unit": "inapplicable"
        },
        "seminvariant": {
            "x-optimade-type": "list",
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
            "description": "FFT grid factors arising from structure seminvariants.",
            "items": {
                "x-optimade-type": "integer",
                "type": [
                    "integer",
                    "null"
                ],
                "description": "One grid factor.",
                "x-optimade-unit": "inapplicable"
            },
            "x-optimade-unit": "inapplicable"
        },
        "euclidean": {
            "x-optimade-type": "list",
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
            "description": "FFT grid factors arising from Euclidean-normalizer considerations.",
            "items": {
                "x-optimade-type": "integer",
                "type": [
                    "integer",
                    "null"
                ],
                "description": "One grid factor.",
                "x-optimade-unit": "inapplicable"
            },
            "x-optimade-unit": "inapplicable"
        }
    },
    "examples": [
        {
            "space_group": [
                1,
                1,
                1
            ],
            "seminvariant": [
                1,
                1,
                1
            ],
            "euclidean": [
                1,
                1,
                1
            ]
        },
        {
            "space_group": [
                1,
                1,
                1
            ],
            "seminvariant": [
                2,
                2,
                2
            ],
            "euclidean": [
                2,
                2,
                2
            ]
        }
    ]
}
```