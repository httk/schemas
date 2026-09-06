# Complex character table (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_complex`](https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_complex.md)**  
**Definition name:** `character_table_complex`

**Property name:** Complex character table  
**Description:** Complex irreducible character table of the crystallographic point group.  
**Type:** list  

Rows correspond to complex irreducible representations and columns follow the order of `conjugacy_classes`.
Each character is stored as a dictionary with string fields `re` and `im` representing its real and imaginary components.
Components can be integers, rational fractions, or algebraic expressions such as `sqrt(3)/2`; they are not restricted to rational fraction strings.
For example, the C3 eigenvalue `exp(2*pi*i/3)` is represented by `re: "-1/2"` and `im: "sqrt(3)/2"`, preserving its algebraic value without replacing the radical by a decimal approximation.

For a representation D and class representative g, the character is `trace(D(g))`; every member of a conjugacy class has the same character.
Each row's character list MUST have length `n_conjugacy_classes`, and its identity-class character MUST equal `dimension`.
The number of complex irreducible rows MUST equal `n_conjugacy_classes`, and the sum of their squared dimensions MUST equal `order`.
The row inner product is weighted by class size: `sum_C size(C)*conj(chi_a(C))*chi_b(C)/order = delta_ab`.
Conjugate one-dimensional rows use distinct `_a` and `_b` label suffixes even when their `label_markup` renderings coincide; join rows by `label`, not by markup.
The current generator places polynomial bases only in `character_table_real`; the optional basis fields retained here are not emitted.
In particular, the real two-dimensional span for a conjugate pair must not be interpreted as a basis for either single complex row.

**Examples:**

- `[{"label": "A", "dimension": 1, "characters": [{"re": "1", "im": "0"}], "frobenius_schur_indicator": 1, "label_markup": {"latex": "A", "unicode": "A"}}]`
- `[{"label": "Ag", "dimension": 1, "characters": [{"re": "1", "im": "0"}, {"re": "1", "im": "0"}], "frobenius_schur_indicator": 1, "label_markup": {"latex": "A_{g}", "unicode": "Ag"}}, {"label": "Au", "dimension": 1, "characters": [{"re": "1", "im": "0"}, {"re": "-1", "im": "0"}], "frobenius_schur_indicator": 1, "label_markup": {"latex": "A_{u}", "unicode": "Au"}}]`
- `[{"label": "A", "dimension": 1, "characters": [{"re": "1", "im": "0"}, {"re": "1", "im": "0"}, {"re": "1", "im": "0"}], "frobenius_schur_indicator": 1, "label_markup": {"latex": "A", "unicode": "A"}}, {"label": "E_a", "dimension": 1, "characters": [{"re": "1", "im": "0"}, {"re": "-1/2", "im": "sqrt(3)/2"}, {"re": "-1/2", "im": "-sqrt(3)/2"}], "frobenius_schur_indicator": 0, "label_markup": {"latex": "E", "unicode": "E"}}, {"label": "E_b", "dimension": 1, "characters": [{"re": "1", "im": "0"}, {"re": "-1/2", "im": "-sqrt(3)/2"}, {"re": "-1/2", "im": "sqrt(3)/2"}], "frobenius_schur_indicator": 0, "label_markup": {"latex": "E", "unicode": "E"}}]`

**Formats:** [[JSON](character_table_complex.json)] [[MD](character_table_complex.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_complex",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Complex character table",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "character_table_complex",
        "label": "character_table_complex_pointgroups"
    },
    "type": [
        "array",
        "null"
    ],
    "description": "Complex irreducible character table of the crystallographic point group.\n\nRows correspond to complex irreducible representations and columns follow the order of `conjugacy_classes`.\nEach character is stored as a dictionary with string fields `re` and `im` representing its real and imaginary components.\nComponents can be integers, rational fractions, or algebraic expressions such as `sqrt(3)/2`; they are not restricted to rational fraction strings.\nFor example, the C3 eigenvalue `exp(2*pi*i/3)` is represented by `re: \"-1/2\"` and `im: \"sqrt(3)/2\"`, preserving its algebraic value without replacing the radical by a decimal approximation.\n\nFor a representation D and class representative g, the character is `trace(D(g))`; every member of a conjugacy class has the same character.\nEach row's character list MUST have length `n_conjugacy_classes`, and its identity-class character MUST equal `dimension`.\nThe number of complex irreducible rows MUST equal `n_conjugacy_classes`, and the sum of their squared dimensions MUST equal `order`.\nThe row inner product is weighted by class size: `sum_C size(C)*conj(chi_a(C))*chi_b(C)/order = delta_ab`.\nConjugate one-dimensional rows use distinct `_a` and `_b` label suffixes even when their `label_markup` renderings coincide; join rows by `label`, not by markup.\nThe current generator places polynomial bases only in `character_table_real`; the optional basis fields retained here are not emitted.\nIn particular, the real two-dimensional span for a conjugate pair must not be interpreted as a basis for either single complex row.",
    "x-optimade-unit": "inapplicable",
    "items": {
        "x-optimade-type": "dictionary",
        "type": [
            "object",
            "null"
        ],
        "description": "One row of a point-group character table.",
        "properties": {
            "label": {
                "x-optimade-type": "string",
                "type": [
                    "string",
                    "null"
                ],
                "description": "Irreducible-representation label.",
                "x-optimade-unit": "inapplicable"
            },
            "label_markup": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/core/string_markups",
                "title": "String markups",
                "x-optimade-type": "dictionary",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "string_markups",
                    "label": "string_markups_core"
                },
                "x-optimade-unit": "inapplicable",
                "type": [
                    "object",
                    "null"
                ],
                "description": "Strings with alternate markup and/or encoding for display rendering.\n\nThe object is intended for display-oriented variants only, a sibling property should be used for canonical plain string value.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **html**: OPTIONAL; String.\n      HTML rendering of the sibling string, using inline HTML elements where needed for typographic structure such as subscripts, superscripts, overlines, fractions, and line breaks.\n\n    - **latex**: OPTIONAL; String.\n      LaTeX rendering of the sibling string, suitable for use with a LaTeX or MathJax-like renderer.\n\n    - **unicode**: OPTIONAL; String.\n      Unicode rendering of the sibling string, using Unicode code points for display features where practical.",
                "properties": {
                    "html": {
                        "x-optimade-type": "string",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "string",
                            "null"
                        ],
                        "description": "HTML rendering of the sibling string."
                    },
                    "latex": {
                        "x-optimade-type": "string",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "string",
                            "null"
                        ],
                        "description": "LaTeX rendering of the sibling string."
                    },
                    "unicode": {
                        "x-optimade-type": "string",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "string",
                            "null"
                        ],
                        "description": "Unicode rendering of the sibling string."
                    }
                },
                "examples": [
                    {
                        "html": "<i>P</i> 2<sub>1</sub>/<i>c</i>",
                        "latex": "\\mathit{P}\\,2_{1}/c",
                        "unicode": "P2\u2081/c"
                    }
                ]
            },
            "dimension": {
                "x-optimade-type": "integer",
                "type": [
                    "integer",
                    "null"
                ],
                "description": "Dimension of the irreducible representation.",
                "x-optimade-unit": "inapplicable"
            },
            "characters": {
                "x-optimade-type": "list",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Characters for the conjugacy classes in table order.",
                "items": {
                    "x-optimade-type": "dictionary",
                    "type": [
                        "object",
                        "null"
                    ],
                    "description": "One complex character value represented as exact real and imaginary parts.",
                    "x-optimade-unit": "inapplicable",
                    "properties": {
                        "re": {
                            "x-optimade-type": "string",
                            "type": [
                                "string",
                                "null"
                            ],
                            "description": "Real component serialized as an integer or rational string for the generated crystallographic tables.",
                            "x-optimade-unit": "inapplicable"
                        },
                        "im": {
                            "x-optimade-type": "string",
                            "type": [
                                "string",
                                "null"
                            ],
                            "description": "Imaginary component serialized as a symbolic real-number string, including signed radicals such as `-sqrt(3)/2`; `0` denotes a real character.",
                            "x-optimade-unit": "inapplicable"
                        }
                    }
                },
                "x-optimade-unit": "inapplicable"
            },
            "frobenius_schur_indicator": {
                "x-optimade-type": "integer",
                "enum": [
                    0,
                    1
                ],
                "type": [
                    "integer",
                    "null"
                ],
                "description": "The complex-irrep indicator `nu = sum_g chi(g^2)/order`.\nThe emitted value 1 means the irrep admits a real realization; 0 means it is of complex type and has a distinct complex-conjugate partner.\nThe crystallographic point groups covered here have no quaternionic-type irreps (whose indicator would be -1).",
                "x-optimade-unit": "inapplicable"
            },
            "basis_linear": {
                "x-optimade-type": "list",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Linear basis polynomials spanning the isotypic component of this representation in the space of linear functions.\nPolynomials use an orthonormal Cartesian frame (x along a, z along c for hexagonal axes) with exact rational coefficients, e.g. `x`, `x+y`.\nThe listed polynomials are linearly independent; repeated copies of a representation are not separated into conventional multiplets.",
                "items": {
                    "x-optimade-type": "string",
                    "type": [
                        "string",
                        "null"
                    ],
                    "description": "One basis polynomial in Cartesian x, y, z with rational coefficients.",
                    "x-optimade-unit": "inapplicable"
                },
                "x-optimade-unit": "inapplicable"
            },
            "basis_rotation": {
                "x-optimade-type": "list",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Axial-vector (rotation) basis polynomials spanning the isotypic component of this representation, in the same Cartesian frame as `basis_linear`, e.g. `Rz`, `Rx+Ry`.",
                "items": {
                    "x-optimade-type": "string",
                    "type": [
                        "string",
                        "null"
                    ],
                    "description": "One basis polynomial in Rx, Ry, Rz with rational coefficients.",
                    "x-optimade-unit": "inapplicable"
                },
                "x-optimade-unit": "inapplicable"
            },
            "basis_quadratic": {
                "x-optimade-type": "list",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Quadratic basis polynomials spanning the isotypic component of this representation in the space of homogeneous quadratic functions, in the same Cartesian frame as `basis_linear`, e.g. `x^2+y^2`, `x^2-y^2`, `xz`.",
                "items": {
                    "x-optimade-type": "string",
                    "type": [
                        "string",
                        "null"
                    ],
                    "description": "One quadratic basis polynomial in x^2, y^2, z^2, xy, xz, yz with rational coefficients.",
                    "x-optimade-unit": "inapplicable"
                },
                "x-optimade-unit": "inapplicable"
            }
        },
        "x-optimade-unit": "inapplicable"
    },
    "examples": [
        [
            {
                "label": "A",
                "dimension": 1,
                "characters": [
                    {
                        "re": "1",
                        "im": "0"
                    }
                ],
                "frobenius_schur_indicator": 1,
                "label_markup": {
                    "latex": "A",
                    "unicode": "A"
                }
            }
        ],
        [
            {
                "label": "Ag",
                "dimension": 1,
                "characters": [
                    {
                        "re": "1",
                        "im": "0"
                    },
                    {
                        "re": "1",
                        "im": "0"
                    }
                ],
                "frobenius_schur_indicator": 1,
                "label_markup": {
                    "latex": "A_{g}",
                    "unicode": "Ag"
                }
            },
            {
                "label": "Au",
                "dimension": 1,
                "characters": [
                    {
                        "re": "1",
                        "im": "0"
                    },
                    {
                        "re": "-1",
                        "im": "0"
                    }
                ],
                "frobenius_schur_indicator": 1,
                "label_markup": {
                    "latex": "A_{u}",
                    "unicode": "Au"
                }
            }
        ],
        [
            {
                "label": "A",
                "dimension": 1,
                "characters": [
                    {
                        "re": "1",
                        "im": "0"
                    },
                    {
                        "re": "1",
                        "im": "0"
                    },
                    {
                        "re": "1",
                        "im": "0"
                    }
                ],
                "frobenius_schur_indicator": 1,
                "label_markup": {
                    "latex": "A",
                    "unicode": "A"
                }
            },
            {
                "label": "E_a",
                "dimension": 1,
                "characters": [
                    {
                        "re": "1",
                        "im": "0"
                    },
                    {
                        "re": "-1/2",
                        "im": "sqrt(3)/2"
                    },
                    {
                        "re": "-1/2",
                        "im": "-sqrt(3)/2"
                    }
                ],
                "frobenius_schur_indicator": 0,
                "label_markup": {
                    "latex": "E",
                    "unicode": "E"
                }
            },
            {
                "label": "E_b",
                "dimension": 1,
                "characters": [
                    {
                        "re": "1",
                        "im": "0"
                    },
                    {
                        "re": "-1/2",
                        "im": "-sqrt(3)/2"
                    },
                    {
                        "re": "-1/2",
                        "im": "sqrt(3)/2"
                    }
                ],
                "frobenius_schur_indicator": 0,
                "label_markup": {
                    "latex": "E",
                    "unicode": "E"
                }
            }
        ]
    ]
}
```