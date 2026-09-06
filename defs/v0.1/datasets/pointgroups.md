# Point groups (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/datasets/pointgroups`](https://schemas.httk.org/defs/v0.1/datasets/pointgroups.md)**  
**Definition name:** `pointgroups`

**Property name:** Point groups  
**Description:** Ordered table of crystallographic point-group records.
Each item contains point-group classification, finite point-group operations, conjugacy classes, and real and complex character tables generated from cctbx and spgrep.  
**Type:** list  

**Requirements/Conventions**:

- The table covers the 32 crystallographic point groups.
- The point-group records are independent of any particular space-group setting.
- Character-table rows use Mulliken labels and include formatted label variants when available.

**Examples:**

- `[{"hm_symbol": "2/m", "order": 4}]`

**Formats:** [[JSON](pointgroups.json)] [[MD](pointgroups.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/datasets/pointgroups",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Point groups",
    "$comment": "Dataset of pointgroup entries.",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "pointgroups",
        "label": "pointgroups_pointgroups"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "array",
        "null"
    ],
    "description": "Ordered table of crystallographic point-group records.\nEach item contains point-group classification, finite point-group operations, conjugacy classes, and real and complex character tables generated from cctbx and spgrep.\n\n**Requirements/Conventions**:\n\n- The table covers the 32 crystallographic point groups.\n- The point-group records are independent of any particular space-group setting.\n- Character-table rows use Mulliken labels and include formatted label variants when available.",
    "items": {
        "$id": "https://schemas.httk.org/defs/v0.1/entrytypes/pointgroups",
        "x-optimade-type": "dictionary",
        "x-optimade-unit": "inapplicable",
        "type": [
            "object",
            "null"
        ],
        "title": "httk point group symmetry fields",
        "x-optimade-definition": {
            "kind": "entrytype",
            "format": "1.3",
            "version": "0.1.0",
            "name": "pointgroups",
            "label": "pointgroups_entrytype_httk"
        },
        "properties": {
            "id": {
                "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/id",
                "x-optimade-requirements": {
                    "support": "must",
                    "sortable": true,
                    "query-support": "all mandatory",
                    "response-level": "always"
                },
                "title": "ID",
                "x-optimade-type": "string",
                "x-optimade-definition": {
                    "label": "id_core",
                    "kind": "property",
                    "version": "1.2.0",
                    "format": "1.2",
                    "name": "id"
                },
                "type": [
                    "string"
                ],
                "description": "A unique string referencing a specific entry in the database.\n\n**Requirements/Conventions:**\n\n- Taken together, the ID and entry type MUST uniquely identify the entry.\n- Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.\n- IDs MAY change over time.",
                "examples": [
                    "db/1234567",
                    "cod/2000000",
                    "cod/2000000@1234567",
                    "nomad/L1234567890",
                    "42"
                ],
                "x-optimade-unit": "inapplicable"
            },
            "type": {
                "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/type",
                "x-optimade-requirements": {
                    "support": "must",
                    "sortable": true,
                    "query-support": "all mandatory",
                    "response-level": "always"
                },
                "title": "type",
                "x-optimade-type": "string",
                "x-optimade-definition": {
                    "label": "type_core",
                    "kind": "property",
                    "version": "1.2.0",
                    "format": "1.2",
                    "name": "type"
                },
                "type": [
                    "string"
                ],
                "description": "The name of the type of an entry.\n\n**Requirements/Conventions:**\n\n- MUST be an existing entry type.\n- The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.",
                "examples": [
                    "structures"
                ],
                "x-optimade-unit": "inapplicable"
            },
            "immutable_id": {
                "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/immutable_id",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "all mandatory",
                    "response-level": "may"
                },
                "title": "immutable ID",
                "x-optimade-type": "string",
                "x-optimade-definition": {
                    "label": "immutable_id_core",
                    "kind": "property",
                    "version": "1.2.0",
                    "format": "1.2",
                    "name": "immutable_id"
                },
                "type": [
                    "string",
                    "null"
                ],
                "description": "The entry's immutable ID (e.g., a UUID).\n\n**Requirements/Conventions:**\n\n- This is important for databases having preferred IDs that point to \"the latest version\" of a record, but still offer access to older variants.\n- This ID maps to the version-specific record, in case it changes in the future.",
                "examples": [
                    "8bd3e750-b477-41a0-9b11-3a799f21b44f",
                    "fjeiwoj,54;@=%<>#32"
                ],
                "x-optimade-unit": "inapplicable"
            },
            "last_modified": {
                "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/last_modified",
                "x-optimade-requirements": {
                    "support": "should",
                    "sortable": false,
                    "query-support": "all mandatory",
                    "response-level": "must"
                },
                "title": "last modified",
                "x-optimade-type": "timestamp",
                "x-optimade-definition": {
                    "label": "last_modified_core",
                    "kind": "property",
                    "version": "1.2.0",
                    "format": "1.2",
                    "name": "last_modified"
                },
                "type": [
                    "string",
                    "null"
                ],
                "format": "date-time",
                "description": "Date and time representing when the entry was last modified.",
                "examples": [
                    "2007-04-05T14:30:20Z"
                ],
                "x-optimade-unit": "inapplicable"
            },
            "character_table_complex": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_complex",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
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
                                1,
                                null
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
            },
            "character_table_real": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/character_table_real",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Real character table",
                "x-optimade-type": "list",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "character_table_real",
                    "label": "character_table_real_pointgroups"
                },
                "type": [
                    "array",
                    "null"
                ],
                "description": "Real irreducible character table of the crystallographic point group.\n\nRows correspond to real irreducible representations and columns follow the order of `conjugacy_classes`.\nCharacters of the real table are exact integers and are therefore stored as plain integers, unlike the symbolic `re`/`im` string pairs of `character_table_complex`.\n\nIrreducibility here is over the real numbers.\nA pair of inequivalent complex-conjugate irreps can combine into one real irrep whose dimension and character are the sums of the constituent dimensions and characters.\nConsequently the number of real rows can be smaller than `n_conjugacy_classes`; such a paired row has character norm two under the class-size-weighted complex character inner product, not one.\nEvery character list MUST follow `conjugacy_classes` and have that list's length, and the identity character MUST equal `dimension`.\nPolynomial bases span each isotypic component, meaning all copies of the indicated real irrep in the chosen polynomial space.\nThe number of listed polynomials can therefore exceed `dimension`, but must be an integer multiple of it.\nLinear and axial spaces each have dimension three; the homogeneous quadratic space has dimension six, including the scalar trace `x^2+y^2+z^2`.\nBasis lists are independent spanning sets, not promised to be orthonormal or partitioned into conventional multiplets; the generator omits a basis field when that irrep is absent from that polynomial space.\nThe coordinates in these polynomial strings are Cartesian variables, unlike the fractional-coordinate variables in `symops`.\nFor a Cartesian operation Q, polar coordinates transform by Q and axial coordinates by `det(Q)*Q`; quadratic polynomials transform by substitution.\nThe final example displays selected A1 and B1 rows of 4mm rather than a complete table; full emitted tables contain every real irrep.",
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
                                "x-optimade-type": "integer",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "One real character value represented as an exact integer.",
                                "x-optimade-unit": "inapplicable"
                            },
                            "x-optimade-unit": "inapplicable"
                        },
                        "frobenius_schur_indicator": {
                            "x-optimade-type": "integer",
                            "type": [
                                "integer",
                                "null"
                            ],
                            "description": "Optional Frobenius-Schur annotation; the current generator does not emit this field in the real table.\nThe indicator convention is defined for complex irreducible rows in `character_table_complex`; do not assume a real row formed from a conjugate pair is itself complex-irreducible or has indicator one.",
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
                                1
                            ],
                            "basis_linear": [
                                "x",
                                "y",
                                "z"
                            ],
                            "basis_rotation": [
                                "Rx",
                                "Ry",
                                "Rz"
                            ],
                            "basis_quadratic": [
                                "x^2",
                                "y^2",
                                "z^2",
                                "xy",
                                "xz",
                                "yz"
                            ],
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
                                1,
                                1
                            ],
                            "basis_rotation": [
                                "Rx",
                                "Ry",
                                "Rz"
                            ],
                            "basis_quadratic": [
                                "x^2",
                                "y^2",
                                "z^2",
                                "xy",
                                "xz",
                                "yz"
                            ],
                            "label_markup": {
                                "latex": "A_{g}",
                                "unicode": "Ag"
                            }
                        },
                        {
                            "label": "Au",
                            "dimension": 1,
                            "characters": [
                                1,
                                -1
                            ],
                            "basis_linear": [
                                "x",
                                "y",
                                "z"
                            ],
                            "label_markup": {
                                "latex": "A_{u}",
                                "unicode": "Au"
                            }
                        }
                    ],
                    [
                        {
                            "label": "A1",
                            "dimension": 1,
                            "characters": [
                                1,
                                1,
                                1,
                                1,
                                1
                            ],
                            "basis_linear": [
                                "z"
                            ],
                            "basis_quadratic": [
                                "x^2+y^2",
                                "z^2"
                            ],
                            "label_markup": {
                                "latex": "A_{1}",
                                "unicode": "A\u2081"
                            }
                        },
                        {
                            "label": "B1",
                            "dimension": 1,
                            "characters": [
                                1,
                                1,
                                -1,
                                1,
                                -1
                            ],
                            "basis_quadratic": [
                                "x^2-y^2"
                            ],
                            "label_markup": {
                                "latex": "B_{1}",
                                "unicode": "B\u2081"
                            }
                        }
                    ]
                ]
            },
            "conjugacy_classes": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/conjugacy_classes",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Conjugacy classes",
                "x-optimade-type": "list",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "conjugacy_classes",
                    "label": "conjugacy_classes_pointgroups"
                },
                "type": [
                    "array",
                    "null"
                ],
                "description": "Conjugacy classes of a crystallographic point group.\n\nEach class lists its member operation indices, a representative operation, a conventional class label, and operation-type metadata used by the character tables.\nOperation indices refer to positions in the `symops` list of the same point-group record, starting at 0.\n\n**Requirements/Conventions**:\n\n- It MUST be a list of dictionaries, one per conjugacy class, ordered consistently with the character tables.\n- **size** MUST equal the length of **members**.\n- **op\\_type** is the signed integer rotation-type code of the representative operation: `1`, `2`, `3`, `4`, `6` for proper rotations, and the negated value for the corresponding rotoinversions, with `-2` denoting a mirror plane.\n\nTwo operations g and h belong to the same class precisely when `h = a*g*a^-1` for an operation a of this point group.\nThe `members` lists MUST partition the indices of `symops`, and `representative` MUST be a member of its class.\nClass sizes therefore sum to `order`.\nThe class order defines character-table columns and must not be changed without applying the same permutation to every character row.\nClass labels use Schoenflies-style rotation-reflection notation: `S_n` combines a rotation through `2*pi/n` with reflection perpendicular to its axis.\nFor odd n the order of `S_n` is `2*n`, so its inverse is `S_n^(2*n-1)`; these powers must not be confused with crystallographic rotoinversion type codes in `op_type`.\nThe reported `op_axis` follows the same direct-lattice direction convention as `symops[representative].axis`; labels are display aids, while the operation matrix fixes the action.",
                "x-optimade-unit": "inapplicable",
                "items": {
                    "x-optimade-type": "dictionary",
                    "type": [
                        "object",
                        "null"
                    ],
                    "description": "One conjugacy class of a crystallographic point group.",
                    "properties": {
                        "label": {
                            "x-optimade-type": "dictionary",
                            "type": [
                                "object",
                                "null"
                            ],
                            "description": "Rendered class label.",
                            "properties": {
                                "ascii": {
                                    "x-optimade-type": "string",
                                    "type": [
                                        "string",
                                        "null"
                                    ],
                                    "description": "Plain-text rendering intended for logs, command-line output, or compact display.",
                                    "x-optimade-unit": "inapplicable"
                                },
                                "unicode": {
                                    "x-optimade-type": "string",
                                    "type": [
                                        "string",
                                        "null"
                                    ],
                                    "description": "Unicode rendering of the same label.",
                                    "x-optimade-unit": "inapplicable"
                                },
                                "latex": {
                                    "x-optimade-type": "string",
                                    "type": [
                                        "string",
                                        "null"
                                    ],
                                    "description": "LaTeX rendering of the same label.",
                                    "x-optimade-unit": "inapplicable"
                                }
                            },
                            "x-optimade-unit": "inapplicable"
                        },
                        "size": {
                            "x-optimade-type": "integer",
                            "type": [
                                "integer",
                                "null"
                            ],
                            "description": "Number of point-group operations in the class. It MUST equal the length of `members`.",
                            "x-optimade-unit": "inapplicable"
                        },
                        "members": {
                            "x-optimade-type": "list",
                            "type": [
                                "array",
                                "null"
                            ],
                            "description": "Indices into the `symops` list of the operations belonging to this class.",
                            "items": {
                                "x-optimade-type": "integer",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Operation index into `symops`.",
                                "x-optimade-unit": "inapplicable"
                            },
                            "x-optimade-unit": "inapplicable"
                        },
                        "representative": {
                            "x-optimade-type": "integer",
                            "type": [
                                "integer",
                                "null"
                            ],
                            "description": "Index into `symops` of a representative operation for the class.",
                            "x-optimade-unit": "inapplicable"
                        },
                        "op_type": {
                            "x-optimade-type": "integer",
                            "type": [
                                "integer",
                                "null"
                            ],
                            "description": "Signed integer rotation-type code of the representative operation; negative values denote rotoinversions, with `-2` denoting a mirror plane.",
                            "enum": [
                                1,
                                -1,
                                2,
                                -2,
                                3,
                                -3,
                                4,
                                -4,
                                6,
                                -6,
                                null
                            ],
                            "x-optimade-unit": "inapplicable"
                        },
                        "op_axis": {
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
                            "description": "Integer-vector axis or invariant direction of the representative operation; `[0, 0, 0]` when no axis is applicable.",
                            "items": {
                                "x-optimade-type": "integer",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "One integer component of the axis vector.",
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
                            "label": {
                                "ascii": "E",
                                "unicode": "E",
                                "latex": "E"
                            },
                            "size": 1,
                            "members": [
                                0
                            ],
                            "representative": 0,
                            "op_type": 1,
                            "op_axis": [
                                0,
                                0,
                                0
                            ]
                        },
                        {
                            "label": {
                                "ascii": "i",
                                "unicode": "i",
                                "latex": "i"
                            },
                            "size": 1,
                            "members": [
                                1
                            ],
                            "representative": 1,
                            "op_type": -1,
                            "op_axis": [
                                0,
                                0,
                                0
                            ]
                        }
                    ]
                ]
            },
            "crystal_system": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
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
            },
            "hm_symbol": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/hm_symbol",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Hermann-Mauguin symbol",
                "x-optimade-type": "string",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "hm_symbol",
                    "label": "hm_symbol_pointgroups"
                },
                "type": [
                    "string",
                    "null"
                ],
                "description": "Hermann-Mauguin point-group symbol used as the key and display symbol for a point-group record.\n\nThe value is one of the 32 crystallographic point-group symbols in Hermann-Mauguin notation, written in ASCII with `-` denoting rotoinversion.",
                "x-optimade-unit": "inapplicable",
                "enum": [
                    "1",
                    "-1",
                    "2",
                    "m",
                    "2/m",
                    "222",
                    "mm2",
                    "mmm",
                    "4",
                    "-4",
                    "4/m",
                    "422",
                    "4mm",
                    "-42m",
                    "4/mmm",
                    "3",
                    "-3",
                    "32",
                    "3m",
                    "-3m",
                    "6",
                    "-6",
                    "6/m",
                    "622",
                    "6mm",
                    "-62m",
                    "6/mmm",
                    "23",
                    "m-3",
                    "432",
                    "-43m",
                    "m-3m",
                    null
                ],
                "examples": [
                    "1",
                    "-1",
                    "m-3m"
                ]
            },
            "is_centrosymmetric": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/is_centrosymmetric",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "is centrosymmetric",
                "$comment": "Generated from data-generators JSON-LD fields without external definition URLs.",
                "x-optimade-type": "boolean",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "is_centrosymmetric",
                    "label": "is_centrosymmetric_pointgroups"
                },
                "type": [
                    "boolean",
                    "null"
                ],
                "description": "Boolean flag indicating whether the point group contains inversion symmetry.",
                "x-optimade-unit": "inapplicable",
                "examples": [
                    false,
                    true
                ]
            },
            "laue_class": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/laue_class",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Laue class",
                "x-optimade-type": "string",
                "x-compatibility": [
                    "https://www.iucr.org/__data/iucr/cifdic_html/2/cif_sym.dic/Ispace_group.Laue_class.html"
                ],
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "laue_class",
                    "label": "laue_class_pointgroups"
                },
                "type": [
                    "string",
                    "null"
                ],
                "description": "The Laue class associated with the space group or point group.\n\nThe Laue class groups point groups that become equivalent when inversion symmetry is included.\n\nIt is the centrosymmetric point-group type generated by the original point group together with inversion.\nIts use as diffraction symmetry invokes the usual Friedel-pair equivalence; anomalous-scattering measurements need not have that intensity symmetry.",
                "x-optimade-unit": "inapplicable",
                "enum": [
                    "-1",
                    "2/m",
                    "mmm",
                    "4/m",
                    "4/mmm",
                    "-3",
                    "-3m",
                    "6/m",
                    "6/mmm",
                    "m-3",
                    "m-3m",
                    null
                ],
                "examples": [
                    "-1",
                    "2/m"
                ]
            },
            "n_conjugacy_classes": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/n_conjugacy_classes",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Number of conjugacy classes",
                "x-optimade-type": "integer",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "n_conjugacy_classes",
                    "label": "n_conjugacy_classes_pointgroups"
                },
                "type": [
                    "integer",
                    "null"
                ],
                "description": "Number of conjugacy classes in the crystallographic point group.\n\nThis value MUST equal the length of the `conjugacy_classes` list of the point-group entry.\n\nIt also equals the number of complex irreducible rows in `character_table_complex`, but need not equal the number of rows in `character_table_real`.",
                "x-optimade-unit": "inapplicable",
                "examples": [
                    1,
                    2
                ]
            },
            "order": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/order",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Order of the point group",
                "x-optimade-type": "integer",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "order",
                    "label": "order_pointgroups"
                },
                "type": [
                    "integer",
                    "null"
                ],
                "description": "Order of the point group, i.e. the number of operations in the finite point group.\n\nThis value MUST equal the length of the `symops` list of the point-group entry.",
                "x-optimade-unit": "inapplicable",
                "examples": [
                    1,
                    2
                ]
            },
            "schoenflies": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/schoenflies",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Schoenflies symbol",
                "x-optimade-type": "string",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "schoenflies",
                    "label": "schoenflies_pointgroups"
                },
                "type": [
                    "string",
                    "null"
                ],
                "description": "The Schoenflies symbol for the crystallographic point group.\n\nThe value is one of the 32 crystallographic point-group symbols in Schoenflies notation, written in ASCII without subscript formatting.\nThe symbol `S6` is used for the point group also known as `C3i`.",
                "x-optimade-unit": "inapplicable",
                "enum": [
                    "C1",
                    "Ci",
                    "C2",
                    "Cs",
                    "C2h",
                    "D2",
                    "C2v",
                    "D2h",
                    "C4",
                    "S4",
                    "C4h",
                    "D4",
                    "C4v",
                    "D2d",
                    "D4h",
                    "C3",
                    "S6",
                    "D3",
                    "C3v",
                    "D3d",
                    "C6",
                    "C3h",
                    "C6h",
                    "D6",
                    "C6v",
                    "D3h",
                    "D6h",
                    "T",
                    "Th",
                    "O",
                    "Td",
                    "Oh",
                    null
                ],
                "examples": [
                    "C1",
                    "C2v",
                    "Oh"
                ]
            },
            "symops": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/symops",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Symmetry operations",
                "x-optimade-type": "list",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "symops",
                    "label": "symops_pointgroups"
                },
                "x-optimade-unit": "inapplicable",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Full list of symmetry-operation descriptors for a point group.\nEach list member is an `op` object as defined by `/defs/v0.1/properties/symmetry/op`.\nPoint-group operations have a zero translation part, so the `screw_glide` and `origin_shift` classification fields are omitted.\n\n**Requirements/Conventions**:\n\n- It MUST be a list of dictionaries.\n- Each dictionary MUST follow the schema inherited from `/defs/v0.1/properties/symmetry/op`.\n\nThe matrices act on fractional column coordinates in the generator's reference lattice frame, not directly on Cartesian vectors.\nIn particular the hexagonal-axis matrices need not satisfy `W^T*W = I` although they are physical isometries of the appropriate metric.\nCharacter traces are independent of this basis choice; Cartesian polynomial bases are documented separately in `character_table_real`.\nThe order of this list is authoritative for operation indices in `conjugacy_classes`.",
                "items": {
                    "$id": "https://schemas.httk.org/defs/v0.1/properties/symmetry/op",
                    "title": "Operation",
                    "x-optimade-type": "dictionary",
                    "x-optimade-definition": {
                        "kind": "property",
                        "version": "0.1.0",
                        "format": "1.3",
                        "name": "op",
                        "label": "op_symmetry"
                    },
                    "x-optimade-unit": "inapplicable",
                    "type": [
                        "object",
                        "null"
                    ],
                    "description": "Information related to a crystallographic operation acting within one coordinate setting.\n\nRepresents an affine_transformation that is a crystallographic operation within one setting.\nThe affine map itself is stored in the embedded `affine_transformation` field.\nThe remaining fields classify the operation crystallographically, for example by rotation type, axis, sense, and screw or glide component.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **affine\\_transformation**: REQUIRED; Dictionary.\n      Exact affine map for the operation.\n      It MUST follow `/defs/v0.1/properties/symmetry/affine_transformation`.\n\n    - **operation\\_kind**: OPTIONAL; String.\n      The value `euclidean` identifies an operation emitted within a Euclidean-normalizer table; ordinary point-group and space-group operation records omit it.\n\n    - **rot\\_type**: OPTIONAL; String.\n      Crystallographic operation-type label for the linear part.\n\n    - **axis**: OPTIONAL; List of 3 Integers.\n      Operation axis or invariant direction using the integer-vector convention returned by the generator.\n\n    - **sense**: OPTIONAL; Integer.\n      Rotation sense/sign convention returned by the generator; `0` is used when no handed rotation sense is applicable.\n\n    - **screw\\_glide**: OPTIONAL; List of 3 Fractions (String).\n      Screw-axis or glide-plane component associated with a space-group affine operation.\n\n    - **origin\\_shift**: OPTIONAL; List of 3 Fractions (String).\n      Origin shift associated with the screw/glide decomposition of a space-group affine operation.\n\n- Whether the operation is proper follows from the sign of the `det` field of `affine_transformation`; no separate properness flag is stored.\n\nWriting the affine part as `(W,w)`, the intrinsic translation `screw_glide = v` is defined by `(W,w)^n = (I,n*v)`, where `n` is the order of `W`.\nThe reported `origin_shift = q` satisfies `(I-W)*q = w-v`; moving the coordinate origin to `q` leaves the intrinsic translation `v`.\nIt locates the symmetry element and is not a second translation to add to `w`.\nFor a proper rotation, `axis` is the integer direction fixed by `W`; for a rotoinversion it is the rotation axis fixed by `-W`, hence for a mirror it is the plane-normal direction.\nThese are direct-lattice direction components, not Cartesian unit vectors or reciprocal-plane indices.\nThe identity and inversion use `[0,0,0]` because neither has a unique axis.\nThe signed `sense` follows cctbx's rotation/rotoinversion convention about that reported axis; converting a rotoinversion to a Schoenflies rotation-reflection symbol can reverse the rotation sense.",
                    "properties": {
                        "affine_transformation": {
                            "$id": "https://schemas.httk.org/defs/v0.1/properties/symmetry/affine_transformation",
                            "title": "Affine transformation",
                            "x-optimade-type": "dictionary",
                            "x-optimade-definition": {
                                "kind": "property",
                                "version": "0.1.0",
                                "format": "1.3",
                                "name": "affine_transformation",
                                "label": "affine_transformation_symmetry"
                            },
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "object",
                                "null"
                            ],
                            "description": "An affine transformation acting on fractional crystallographic coordinates.\n\nAn invertible affine transformation preserves collinearity and parallelism, but need not preserve Euclidean distances or angles.\nA singular affine map can collapse a line or plane to a lower-dimensional image.\nThe transformation is represented by a 3 by 3 matrix and a 3-vector, both serialized with exact string entries.\nWith column vectors, the map is `u_out = matrix * u_in + vector`; matrix rows specify the three output components.\nThe containing property identifies whether `u_in` denotes fractional coordinates or abstract Wyckoff parameters and identifies the input and output settings.\nNo wrapping modulo lattice translations is implicit in this equation; apply any required periodic reduction only in the specified output setting.\nThe transformation may, for example, represent an operation within one setting, a setting transform, a subgroup embedding, a normalizer representative, or a parametric coordinate map for a Wyckoff-position orbit representative.\nWhen used as a parametric coordinate map, the matrix may be singular because special Wyckoff positions can constrain or identify parameters.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **matrix**: REQUIRED; Exact 3x3 matrix.\n      Matrix part of the affine transformation.\n      It MUST be represented as a list of three row lists, each containing three exact rational entries represented as strings.\n\n    - **vector**: REQUIRED; List of 3 Fractions (String).\n      Translation or origin-shift vector of the affine transformation in fractional coordinates.\n\n    - **xyz**: OPTIONAL; String.\n      Coordinate expression for the affine transformation in `x,y,z` notation when available.\n      It MUST express the same affine map as `matrix` and `vector`, using `x,y,z` for the input components.\n\n    - **det**: OPTIONAL; Integer.\n      Determinant of `matrix` when the generator emits it.\n\n    - **is\\_orthogonal**: OPTIONAL; Boolean.\n      Whether the linear part preserves the crystallographic metric family specified by the containing setting; this is not a test of the fractional matrix against the Cartesian identity metric.",
                            "properties": {
                                "matrix": {
                                    "x-optimade-type": "list",
                                    "x-optimade-unit": "inapplicable",
                                    "x-optimade-dimensions": {
                                        "names": [
                                            "dim_lattice",
                                            "dim_lattice"
                                        ],
                                        "sizes": [
                                            3,
                                            3
                                        ]
                                    },
                                    "type": [
                                        "array",
                                        "null"
                                    ],
                                    "description": "Exact 3 by 3 matrix part of the affine transformation.",
                                    "items": {
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
                                            "array"
                                        ],
                                        "description": "One row of the exact 3 by 3 matrix.",
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
                                    }
                                },
                                "vector": {
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
                                    "description": "Exact fractional-coordinate vector part of the affine transformation.",
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
                                "xyz": {
                                    "$id": "https://schemas.httk.org/defs/v0.1/properties/symmetry/op_xyz",
                                    "title": "Operation xyz",
                                    "x-optimade-type": "string",
                                    "x-compatibility": [
                                        "https://schemas.optimade.org/defs/v1.2/properties/optimade/common/symmetry_operation_xyz",
                                        "https://www.iucr.org/__data/iucr/cifdic_html/2/cif_sym.dic/Ispace_group_symop.operation_xyz.html"
                                    ],
                                    "x-optimade-definition": {
                                        "kind": "property",
                                        "version": "0.1.0",
                                        "format": "1.3",
                                        "name": "op_xyz",
                                        "label": "op_xyz_symmetry"
                                    },
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "string",
                                        "null"
                                    ],
                                    "description": "Coordinate operation expressed in the algebraic xyz form, also known as Jones' faithful representation (Bradley & Cracknell, 1972: pp. 35-37; adapted for computer strings).\n\nThe following definition is adapted from (and meant to be compatible with) the IUCr symCIF version 1.0.1 dictionary definition of `_space_group_symop.operation_xyz` referenced to: International Tables for Crystallography (2002). Volume A, Space-group symmetry, edited by Th. Hahn, 5th. ed. (Kluwer Academic Publishers).\nIt is available at: https://www.iucr.org/__data/iucr/cifdic_html/2/cif_sym.dic/Ispace_group_symop.operation_xyz.html\n\nIf W is a matrix representation of the rotational part of the symmetry operation defined by the positions and signs of x, y and z, and w is a column of translations defined by the fractions, an equivalent position X' is generated from a given position X by the equation: X' = WX + w.",
                                    "x-undef-pattern": "^([-+]?[xyz]([-+][xyz])?([-+](1/2|[12]/3|[1-3]/4|[1-5]/6))?|[-+]?(1/2|[12]/3|[1-3]/4|[1-5]/6)([-+][xyz]([-+][xyz])?)?),([-+]?[xyz]([-+][xyz])?([-+](1/2|[12]/3|[1-3]/4|[1-5]/6))?|[-+]?(1/2|[12]/3|[1-3]/4|[1-5]/6)([-+][xyz]([-+][xyz])?)?),([-+]?[xyz]([-+][xyz])?([-+](1/2|[12]/3|[1-3]/4|[1-5]/6))?|[-+]?(1/2|[12]/3|[1-3]/4|[1-5]/6)([-+][xyz]([-+][xyz])?)?)$",
                                    "examples": [
                                        "-x,-y,z",
                                        "x,1/2-y,1/2+z"
                                    ]
                                },
                                "det": {
                                    "x-optimade-type": "integer",
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "integer",
                                        "null"
                                    ],
                                    "description": "Determinant of the matrix part when emitted by the generator.\nThis optional integer annotation MUST equal the exact determinant of `matrix`; its absence does not imply determinant one.\nRational matrices can have noninteger determinants, in which case this integer annotation is omitted."
                                },
                                "is_orthogonal": {
                                    "x-optimade-type": "boolean",
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "boolean",
                                        "null"
                                    ],
                                    "description": "Whether the matrix part is an isometry of the setting's metric, i.e. it preserves every metric tensor of the setting's crystal family expressed in this basis.\nFor a same-setting matrix `M` and metric tensor `g`, the criterion is `M^T g M = g` for every positive-definite metric in that family.\nThis is orthogonality with respect to the actual (generally non-Cartesian) lattice metric, not orthogonality of the matrix as a plain array: hexagonal sixfold rotations are isometries, whereas a cell-enlarging transform is not."
                                }
                            },
                            "examples": [
                                {
                                    "matrix": [
                                        [
                                            "-1",
                                            "0",
                                            "0"
                                        ],
                                        [
                                            "0",
                                            "-1",
                                            "0"
                                        ],
                                        [
                                            "0",
                                            "0",
                                            "1"
                                        ]
                                    ],
                                    "vector": [
                                        "0",
                                        "0",
                                        "0"
                                    ],
                                    "xyz": "-x,-y,z",
                                    "det": 1,
                                    "is_orthogonal": true
                                }
                            ]
                        },
                        "operation_kind": {
                            "x-optimade-type": "string",
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "string"
                            ],
                            "enum": [
                                "euclidean"
                            ],
                            "description": "Euclidean-normalizer context when present; this does not change the operation's affine action."
                        },
                        "rot_type": {
                            "x-optimade-type": "string",
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "string",
                                "null"
                            ],
                            "description": "Symbolic crystallographic operation-type label for the linear part.",
                            "enum": [
                                "1",
                                "-1",
                                "2",
                                "m",
                                "3",
                                "-3",
                                "4",
                                "-4",
                                "6",
                                "-6",
                                null
                            ]
                        },
                        "axis": {
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
                            "description": "Integer-vector axis or invariant-direction descriptor for the operation.",
                            "items": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer"
                                ],
                                "description": "One integer component of the axis vector."
                            }
                        },
                        "sense": {
                            "x-optimade-type": "integer",
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "integer",
                                "null"
                            ],
                            "description": "Rotation sense/sign convention returned by the generator; zero for identity, inversion, twofold rotation, and mirror operations.",
                            "enum": [
                                -1,
                                0,
                                1,
                                null
                            ]
                        },
                        "screw_glide": {
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
                            "description": "Screw-axis or glide-plane component represented exactly as a list of fraction strings.",
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
                        "origin_shift": {
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
                            "description": "Origin-shift descriptor represented exactly as a list of fraction strings.",
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
                        }
                    },
                    "examples": [
                        {
                            "affine_transformation": {
                                "matrix": [
                                    [
                                        "-1",
                                        "0",
                                        "0"
                                    ],
                                    [
                                        "0",
                                        "-1",
                                        "0"
                                    ],
                                    [
                                        "0",
                                        "0",
                                        "1"
                                    ]
                                ],
                                "vector": [
                                    "0",
                                    "0",
                                    "0"
                                ],
                                "xyz": "-x,-y,z",
                                "det": 1,
                                "is_orthogonal": true
                            },
                            "rot_type": "2",
                            "sense": 0,
                            "axis": [
                                0,
                                0,
                                1
                            ],
                            "screw_glide": [
                                "0",
                                "0",
                                "0"
                            ],
                            "origin_shift": [
                                "0",
                                "0",
                                "0"
                            ]
                        }
                    ]
                },
                "examples": [
                    [
                        {
                            "affine_transformation": {
                                "matrix": [
                                    [
                                        "1",
                                        "0",
                                        "0"
                                    ],
                                    [
                                        "0",
                                        "1",
                                        "0"
                                    ],
                                    [
                                        "0",
                                        "0",
                                        "1"
                                    ]
                                ],
                                "vector": [
                                    "0",
                                    "0",
                                    "0"
                                ],
                                "xyz": "x,y,z",
                                "det": 1,
                                "is_orthogonal": true
                            },
                            "rot_type": "1",
                            "sense": 0,
                            "axis": [
                                0,
                                0,
                                0
                            ]
                        }
                    ]
                ]
            },
            "schoenflies_markup": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/schoenflies_markup",
                "x-optimade-requirements": {
                    "support": "may",
                    "sortable": false,
                    "query-support": "none",
                    "response-level": "may"
                },
                "title": "Schoenflies symbol markups",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "schoenflies_markup",
                    "label": "schoenflies_markup_pointgroups"
                },
                "description": "Display-oriented renderings of the Schoenflies symbol in `schoenflies`.\nThe plain string value is stored in the corresponding unsuffixed property; this object only provides alternate markup forms for display.",
                "x-optimade-type": "dictionary",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "object",
                    "null"
                ],
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
            }
        }
    },
    "examples": [
        [
            {
                "hm_symbol": "2/m",
                "order": 4
            }
        ]
    ]
}
```