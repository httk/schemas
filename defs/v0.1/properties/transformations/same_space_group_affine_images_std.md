# Same-space-group affine images in the standard setting (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/transformations/same_space_group_affine_images_std`](https://schemas.httk.org/defs/v0.1/properties/transformations/same_space_group_affine_images_std.md)**  
**Definition name:** `same_space_group_affine_images_std`

**Property name:** Same-space-group affine images in the standard setting  
**Description:** Same-space-group affine-image record for one International Tables standard setting.  
**Type:** dictionary  

**Requirements/Conventions**:

- It MUST be a dictionary with the following keys:

    - **it\_number**: REQUIRED; Integer.
      International Tables space-group number for the standard setting.

    - **hall**: REQUIRED; String.
      Normalized Hall-entry key of the reference setting used for the standard setting.
      This historical field name contains a lookup key, following `hall_entry`, rather than the display Hall symbol normally stored as `hall`.

    - **affine\_images**: REQUIRED; List of dictionaries.
      Same-space-group affine images represented by exact `matrix` and `vector` transforms.

The generated pool contains identity, the finite Euclidean-normalizer operations, inverses of the bounded isomorphic-subgroup embeddings, and all pairwise compositions of that base pool.
The list is deduplicated using exact matrices and translations reduced modulo integer cell translations; it is not a closure under arbitrarily long compositions.
Each item acts directly as `x_image = matrix*x + vector` in the named standard basis.
Inverse subgroup embeddings can have noninteger determinants and change the periodic cell description, so these maps must not all be interpreted as same-cell symmetry or normalizer operations.

**Examples:**

- `{"it_number": 1, "hall": "p_1", "affine_images": [{"affine_transformation": {"matrix": [["1", "0", "0"], ["0", "1", "0"], ["0", "0", "1"]], "vector": ["0", "0", "0"]}}]}`

**Formats:** [[JSON](same_space_group_affine_images_std.json)] [[MD](same_space_group_affine_images_std.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/same_space_group_affine_images_std",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Same-space-group affine images in the standard setting",
    "x-optimade-type": "dictionary",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "same_space_group_affine_images_std",
        "label": "same_space_group_affine_images_std_transformations"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "object",
        "null"
    ],
    "description": "Same-space-group affine-image record for one International Tables standard setting.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **it\\_number**: REQUIRED; Integer.\n      International Tables space-group number for the standard setting.\n\n    - **hall**: REQUIRED; String.\n      Normalized Hall-entry key of the reference setting used for the standard setting.\n      This historical field name contains a lookup key, following `hall_entry`, rather than the display Hall symbol normally stored as `hall`.\n\n    - **affine\\_images**: REQUIRED; List of dictionaries.\n      Same-space-group affine images represented by exact `matrix` and `vector` transforms.\n\nThe generated pool contains identity, the finite Euclidean-normalizer operations, inverses of the bounded isomorphic-subgroup embeddings, and all pairwise compositions of that base pool.\nThe list is deduplicated using exact matrices and translations reduced modulo integer cell translations; it is not a closure under arbitrarily long compositions.\nEach item acts directly as `x_image = matrix*x + vector` in the named standard basis.\nInverse subgroup embeddings can have noninteger determinants and change the periodic cell description, so these maps must not all be interpreted as same-cell symmetry or normalizer operations.",
    "properties": {
        "it_number": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/it_number",
            "title": "International Tables space-group number",
            "x-optimade-type": "integer",
            "x-compatibility": [
                "https://schemas.optimade.org/defs/v1.2/properties/optimade/structures/space_group_it_number"
            ],
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "it_number",
                "label": "it_number_spacegroups"
            },
            "type": [
                "integer",
                "null"
            ],
            "description": "The International Tables space-group number.\n\nThis integer identifies the space-group type numbered 1 through 230 in International Tables for Crystallography. Multiple Hall settings can share the same `it_number`.",
            "x-optimade-unit": "inapplicable",
            "examples": [
                1,
                5
            ]
        },
        "hall": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/hall_entry",
            "title": "Hall entry",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "hall_entry",
                "label": "hall_entry_spacegroups"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "Normalized Hall-table entry key used internally by the generated datasets.\n\nThe value is derived from the Hall symbol by using lowercase letters and underscores in place of spaces. It is stable for lookup within these data files, while the display Hall symbol is provided separately by `hall` and its formatted variants.\n\n**Requirements/Conventions**:\n\n- This field identifies a concrete Hall setting, not only an IT space-group type.\n- The same value is normally used as the key of the containing `spacegroups` map.\n\nThe normalization is `hall.strip().replace(\" \", \"_\").lower()`; signs, quotes, asterisks, and origin-shift notation are retained.\nThe key is a coordinate-setting identifier, not a numeric spglib Hall number.\nDifferent conventional H-M entry labels can resolve to the same Hall-entry record.",
            "x-optimade-unit": "inapplicable",
            "examples": [
                "p_1",
                "-p_1"
            ]
        },
        "affine_images": {
            "x-optimade-type": "list",
            "x-optimade-unit": "inapplicable",
            "type": [
                "array",
                "null"
            ],
            "description": "Same-space-group affine image transforms.",
            "items": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/symmetry/basis_transform",
                "title": "Basis transformation",
                "x-optimade-type": "dictionary",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "basis_transform",
                    "label": "basis_transform_symmetry"
                },
                "x-optimade-unit": "inapplicable",
                "type": [
                    "object",
                    "null"
                ],
                "description": "One crystallographic transform between coordinate descriptions, settings, cells, or related group embeddings.\n\nThe affine map itself is stored in the embedded `affine_transformation` field.\nThe parent property defines the source and target coordinate systems and the precise role of the transform.\nFor a subgroup embedding the convention is `x_G = P*x_H + p`, where `P = affine_transformation.matrix` and `p = affine_transformation.vector`.\nThe columns of `P` are the subgroup cell vectors expressed in the parent fractional basis, and `p` is the subgroup origin expressed in that basis.\nThus conversion of parent coordinates to subgroup coordinates uses `x_H = P^-1*(x_G-p)`, not the forward affine map.\nUseful, for example, for representing setting changes, subgroup embeddings, isomorphic subgroup transforms, normalizer representatives, and same-space-group affine images.\nThis property is not limited to symmetry operations within one fixed setting; the matrix may be non-orthogonal or have determinant different from one when the transform changes cell or basis.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **affine\\_transformation**: REQUIRED; Dictionary.\n      Exact affine map for the transform, using exact rational matrix and vector entries.\n      The coordinate convention and source/target interpretation are supplied by the parent property.\n\n    - **index**: OPTIONAL; Integer or null.\n      Index metadata whose interpretation is defined by the parent property.\n      Common uses include the subgroup index for subgroup embeddings, the cell index for isomorphic subgroup transforms, or an ordinal representative index in a finite transform table.\n\n    - **subgroup\\_type**: OPTIONAL; String.\n      Translation/point-symmetry classification when supplied for a subgroup embedding.\n      The value MUST be `t` for a translationengleiche subgroup or `k` for a klassengleiche subgroup.\n      It MUST be omitted for identity embeddings and general subgroups that lose both translations and point symmetry, and for transforms that are not subgroup embeddings.\n      Presence of `t` or `k` alone does not certify maximality; the containing relation table supplies that information.\n\n    - **k\\_subtype**: OPTIONAL; String or null.\n      Klassengleiche subtype when the transform describes a klassengleiche subgroup relation.\n      The value MUST be `loss_of_centering_translation` or `enlarged_unit_cell` for klassengleiche relations and null or omitted otherwise.\n\n    - **compatible\\_systems**: OPTIONAL; List of strings.\n      Reference-setting metric families whose every metric tensor is preserved by the linear part after transport to the actual setting basis.\n      This is used for bounded affine normalizer representatives.\n\n    - **operation\\_kind**: OPTIONAL; String.\n      Categorical label for normalizer-type representatives.\n      The value MUST be `euclidean` for Euclidean normalizer operations, `orthogonal_affine` for the signed-permutation affine normalizer subset, or `affine` for the bounded unimodular affine normalizer table.\n      It MUST be omitted when the transform is a setting transform, subgroup embedding, or other transform for which no normalizer operation class applies.\n\n    - **wyckoff\\_splitting**: OPTIONAL; List.\n      Wyckoff-position splitting metadata induced by the transform when available.\n      The list is grouped by explicit parent Wyckoff letter.\n\n    - **criteria**: OPTIONAL; List.\n      Backward-lift constraint metadata induced by the transform when available.\n      The list is grouped by explicit parent Wyckoff letter.",
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
                    "index": {
                        "x-optimade-type": "integer",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "integer",
                            "null"
                        ],
                        "description": "Index metadata whose interpretation is supplied by the parent property."
                    },
                    "subgroup_type": {
                        "x-optimade-type": "string",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "string"
                        ],
                        "description": "International Tables subgroup-type label when applicable.",
                        "enum": [
                            "t",
                            "k"
                        ]
                    },
                    "k_subtype": {
                        "x-optimade-type": "string",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "string",
                            "null"
                        ],
                        "description": "Klassengleiche subtype when applicable; follows the cell-dependent convention defined in `/defs/v0.1/properties/transformations/k_subtype`.",
                        "enum": [
                            "loss_of_centering_translation",
                            "enlarged_unit_cell",
                            null
                        ]
                    },
                    "compatible_systems": {
                        "x-optimade-type": "list",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "array",
                            "null"
                        ],
                        "description": "Crystal metric families, named by reference-setting crystal system, whose metric tensors are all preserved by the transform.\nEach family is the full linear space of metric tensors of that crystal system in the reference setting (including unconstrained cross terms), transported to the basis of the actual setting.\nMonoclinic reference metrics use unique axis b; trigonal and hexagonal reference metrics both use hexagonal axes with a = b and gamma = 120 degrees.\nThese labels describe the tested metric families, not a reassignment of the space group's crystal system or the accidental metric symmetry of a particular specimen.",
                        "items": {
                            "x-optimade-type": "string",
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "string"
                            ],
                            "description": "One compatible crystal-system label.",
                            "enum": [
                                "triclinic",
                                "monoclinic",
                                "orthorhombic",
                                "tetragonal",
                                "trigonal",
                                "hexagonal",
                                "cubic"
                            ]
                        }
                    },
                    "operation_kind": {
                        "x-optimade-type": "string",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "string"
                        ],
                        "description": "Categorical label for normalizer-type representatives.",
                        "enum": [
                            "euclidean",
                            "orthogonal_affine",
                            "affine"
                        ]
                    },
                    "wyckoff_splitting": {
                        "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/wyckoff_splitting",
                        "title": "Wyckoff splitting",
                        "x-optimade-type": "list",
                        "x-optimade-definition": {
                            "kind": "property",
                            "version": "0.1.0",
                            "format": "1.3",
                            "name": "wyckoff_splitting",
                            "label": "wyckoff_splitting_transformations"
                        },
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "array",
                            "null"
                        ],
                        "description": "Wyckoff-position splitting data associated with a subgroup or same-space-group transform.\n\nEach list item gives the split of one parent Wyckoff position.\nThe parent Wyckoff letter is stored in the `parent` field rather than as a JSON dictionary key.\n\n**Requirements/Conventions**:\n\n- It MUST be a list of dictionaries.\n- Each dictionary MUST contain `parent`, the Wyckoff letter in the parent setting.\n- Each dictionary MUST contain `splits`, an ordered list of subgroup Wyckoff-position assignments, each carrying its target representative expression and exact affine map.\n\nFor an embedding `x_G = P*x_H + p`, the split records partition the parent orbit, expressed in the subgroup cell, into distinct subgroup orbits.\nFor each piece let `A` be the first three columns of `affine` and `b` its last column.\nThen `q_H = A*q_G + b`, where `q_G` is a fractional coordinate on the parent's published `first_orbit` branch and `q_H` is on the child's published representative branch.\nThe input is the actual parent representative coordinate, not its free-parameter vector; first evaluate the parent's `orbit[0]` map when starting from parameters.\nThe piece's `xyz` names the child representative branch and MUST equal that child's `first_orbit`; it is not a rendering of the piece's `affine` map on parent coordinates.\nRepeated child letters are meaningful: they identify different child orbits with the same Wyckoff type and MUST NOT be deduplicated by letter.\nFor generic parent parameters, expanding all split pieces under the subgroup gives disjoint orbits whose union is the transformed parent orbit in the subgroup cell.\nTheir multiplicities sum to `abs(det(P)) * parent_multiplicity`; this factor accounts for the cells and is not generally the full subgroup index.\nKeep the exact affine offsets when evaluating the maps; wrapping parent coordinates before applying a non-unimodular map can select a different child orbit.",
                        "items": {
                            "x-optimade-type": "dictionary",
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "object"
                            ],
                            "description": "Splitting data for one parent Wyckoff position.",
                            "required": [
                                "parent",
                                "splits"
                            ],
                            "properties": {
                                "parent": {
                                    "x-optimade-type": "string",
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "string"
                                    ],
                                    "description": "Parent Wyckoff letter."
                                },
                                "splits": {
                                    "x-optimade-type": "list",
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "array"
                                    ],
                                    "description": "Ordered split records for this parent Wyckoff letter.",
                                    "items": {
                                        "x-optimade-type": "dictionary",
                                        "x-optimade-unit": "inapplicable",
                                        "type": [
                                            "object"
                                        ],
                                        "description": "One Wyckoff split record.",
                                        "required": [
                                            "letter",
                                            "xyz",
                                            "affine"
                                        ],
                                        "properties": {
                                            "letter": {
                                                "x-optimade-type": "string",
                                                "x-optimade-unit": "inapplicable",
                                                "type": [
                                                    "string"
                                                ],
                                                "description": "Subgroup Wyckoff letter assigned by this split branch."
                                            },
                                            "xyz": {
                                                "x-optimade-type": "string",
                                                "x-optimade-unit": "inapplicable",
                                                "type": [
                                                    "string"
                                                ],
                                                "description": "Coordinate expression for the split branch."
                                            },
                                            "affine": {
                                                "x-optimade-type": "list",
                                                "x-optimade-unit": "inapplicable",
                                                "x-optimade-dimensions": {
                                                    "names": [
                                                        "dim_lattice",
                                                        "dim_affine"
                                                    ],
                                                    "sizes": [
                                                        3,
                                                        4
                                                    ]
                                                },
                                                "type": [
                                                    "array"
                                                ],
                                                "description": "Exact affine representation for the split branch as a 3 by 4 augmented matrix.\nEach row holds the three linear coefficients followed by the translation component, all as exact fraction strings.",
                                                "items": {
                                                    "x-optimade-type": "list",
                                                    "x-optimade-unit": "inapplicable",
                                                    "x-optimade-dimensions": {
                                                        "names": [
                                                            "dim_affine"
                                                        ],
                                                        "sizes": [
                                                            4
                                                        ]
                                                    },
                                                    "type": [
                                                        "array"
                                                    ],
                                                    "description": "One row of the augmented affine matrix.",
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
                                            }
                                        }
                                    }
                                }
                            }
                        },
                        "examples": [
                            [
                                {
                                    "parent": "a",
                                    "splits": [
                                        {
                                            "letter": "a",
                                            "xyz": "x,y,z",
                                            "affine": [
                                                [
                                                    "1",
                                                    "0",
                                                    "0",
                                                    "0"
                                                ],
                                                [
                                                    "0",
                                                    "1",
                                                    "0",
                                                    "0"
                                                ],
                                                [
                                                    "0",
                                                    "0",
                                                    "1/2",
                                                    "0"
                                                ]
                                            ]
                                        },
                                        {
                                            "letter": "a",
                                            "xyz": "x,y,z",
                                            "affine": [
                                                [
                                                    "1",
                                                    "0",
                                                    "0",
                                                    "0"
                                                ],
                                                [
                                                    "0",
                                                    "1",
                                                    "0",
                                                    "0"
                                                ],
                                                [
                                                    "0",
                                                    "0",
                                                    "1/2",
                                                    "1/2"
                                                ]
                                            ]
                                        }
                                    ]
                                }
                            ]
                        ]
                    },
                    "criteria": {
                        "x-optimade-type": "list",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "array",
                            "null"
                        ],
                        "description": "Backward-lift constraints for each parent Wyckoff position under this particular subgroup embedding.\nFor a fixed parent entry, every constraint MUST hold on the assigned subgroup representative coordinates modulo integer cell translations.\nThese are geometric coordinate conditions, conditional on the specified split roles and their Wyckoff branches; chemical species, occupancies, and matching an entire structure require separate checks.\nAn empty `constraints` list means no additional equations beyond the selected subgroup branches; it does not mean that no split roles are needed.\nThe first example is the generated I4/mmm (139) to P4/mmm (123) index-2 embedding: parent `a` splits into `a` and `d` with no equations, and parent `n` splits into `s` and `t` whose x and z coordinates must differ by 1/2 modulo 1.",
                        "items": {
                            "x-optimade-type": "dictionary",
                            "x-optimade-unit": "inapplicable",
                            "type": [
                                "object"
                            ],
                            "description": "Backward-lift constraints for one parent Wyckoff position.",
                            "required": [
                                "parent",
                                "constraints"
                            ],
                            "properties": {
                                "parent": {
                                    "x-optimade-type": "string",
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "string"
                                    ],
                                    "description": "Parent Wyckoff letter."
                                },
                                "constraints": {
                                    "x-optimade-type": "list",
                                    "x-optimade-unit": "inapplicable",
                                    "type": [
                                        "array"
                                    ],
                                    "description": "Constraint records for this parent Wyckoff letter.",
                                    "items": {
                                        "x-optimade-type": "dictionary",
                                        "x-optimade-unit": "inapplicable",
                                        "type": [
                                            "object"
                                        ],
                                        "description": "One modular equation `sum_i dot(coeffs[i][0], q_i) = target[0] (mod 1)`.\nHere `q_i` is the three-component fractional coordinate on the published subgroup representative branch selected by `roles[i]`, not a local parameter vector or an arbitrary symmetry-equivalent site.\nThe current generator emits one scalar equation per record: `target` has length one, `coeffs` has one item per role, and each item contains one three-component row.\nThe coefficient entries are integer-valued exact strings, which makes the equation invariant under independent integer translations of the role coordinates.",
                                        "properties": {
                                            "roles": {
                                                "x-optimade-type": "list",
                                                "x-optimade-unit": "inapplicable",
                                                "type": [
                                                    "array"
                                                ],
                                                "description": "Wyckoff-position role references entering the constraint.",
                                                "items": {
                                                    "x-optimade-type": "dictionary",
                                                    "x-optimade-unit": "inapplicable",
                                                    "type": [
                                                        "object"
                                                    ],
                                                    "description": "One role reference.",
                                                    "required": [
                                                        "letter",
                                                        "index"
                                                    ],
                                                    "properties": {
                                                        "letter": {
                                                            "x-optimade-type": "string",
                                                            "x-optimade-unit": "inapplicable",
                                                            "type": [
                                                                "string"
                                                            ],
                                                            "description": "Wyckoff letter for the referenced role."
                                                        },
                                                        "index": {
                                                            "x-optimade-type": "integer",
                                                            "x-optimade-unit": "inapplicable",
                                                            "type": [
                                                                "integer"
                                                            ],
                                                            "description": "Zero-based occurrence index among split pieces having this same letter in the corresponding parent's ordered `splits` list, not an index into all pieces or into the overall Wyckoff table."
                                                        }
                                                    }
                                                }
                                            },
                                            "coeffs": {
                                                "x-optimade-type": "list",
                                                "x-optimade-unit": "inapplicable",
                                                "type": [
                                                    "array"
                                                ],
                                                "description": "Exact integer-valued coefficient rows, in the same order as `roles`.",
                                                "items": {
                                                    "x-optimade-type": "list",
                                                    "x-optimade-unit": "inapplicable",
                                                    "type": [
                                                        "array"
                                                    ],
                                                    "description": "Coefficients associated with one role.",
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
                                                        "description": "One exact coefficient vector.",
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
                                                }
                                            },
                                            "target": {
                                                "x-optimade-type": "list",
                                                "x-optimade-unit": "inapplicable",
                                                "type": [
                                                    "array"
                                                ],
                                                "description": "One-element list containing the exact right-hand side modulo one, normalized to the interval [0,1).",
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
                                        }
                                    }
                                }
                            }
                        }
                    }
                },
                "examples": [
                    {
                        "index": 2,
                        "subgroup_type": "k",
                        "k_subtype": "loss_of_centering_translation",
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
                            "xyz": "x,y,z"
                        },
                        "wyckoff_splitting": [
                            {
                                "parent": "a",
                                "splits": [
                                    {
                                        "letter": "a",
                                        "xyz": "0,0,0",
                                        "affine": [
                                            [
                                                "1",
                                                "0",
                                                "0",
                                                "0"
                                            ],
                                            [
                                                "0",
                                                "1",
                                                "0",
                                                "0"
                                            ],
                                            [
                                                "0",
                                                "0",
                                                "1",
                                                "0"
                                            ]
                                        ]
                                    },
                                    {
                                        "letter": "d",
                                        "xyz": "1/2,1/2,1/2",
                                        "affine": [
                                            [
                                                "1",
                                                "0",
                                                "0",
                                                "1/2"
                                            ],
                                            [
                                                "0",
                                                "1",
                                                "0",
                                                "1/2"
                                            ],
                                            [
                                                "0",
                                                "0",
                                                "1",
                                                "1/2"
                                            ]
                                        ]
                                    }
                                ]
                            },
                            {
                                "parent": "n",
                                "splits": [
                                    {
                                        "letter": "s",
                                        "xyz": "x,0,z",
                                        "affine": [
                                            [
                                                "0",
                                                "-1",
                                                "0",
                                                "0"
                                            ],
                                            [
                                                "-1",
                                                "0",
                                                "0",
                                                "0"
                                            ],
                                            [
                                                "0",
                                                "0",
                                                "-1",
                                                "0"
                                            ]
                                        ]
                                    },
                                    {
                                        "letter": "t",
                                        "xyz": "x,1/2,z",
                                        "affine": [
                                            [
                                                "0",
                                                "-1",
                                                "0",
                                                "1/2"
                                            ],
                                            [
                                                "-1",
                                                "0",
                                                "0",
                                                "1/2"
                                            ],
                                            [
                                                "0",
                                                "0",
                                                "-1",
                                                "1/2"
                                            ]
                                        ]
                                    }
                                ]
                            }
                        ],
                        "criteria": [
                            {
                                "parent": "a",
                                "constraints": []
                            },
                            {
                                "parent": "n",
                                "constraints": [
                                    {
                                        "roles": [
                                            {
                                                "letter": "s",
                                                "index": 0
                                            },
                                            {
                                                "letter": "t",
                                                "index": 0
                                            }
                                        ],
                                        "coeffs": [
                                            [
                                                [
                                                    "0",
                                                    "0",
                                                    "1"
                                                ]
                                            ],
                                            [
                                                [
                                                    "0",
                                                    "0",
                                                    "-1"
                                                ]
                                            ]
                                        ],
                                        "target": [
                                            "1/2"
                                        ]
                                    },
                                    {
                                        "roles": [
                                            {
                                                "letter": "s",
                                                "index": 0
                                            },
                                            {
                                                "letter": "t",
                                                "index": 0
                                            }
                                        ],
                                        "coeffs": [
                                            [
                                                [
                                                    "1",
                                                    "0",
                                                    "0"
                                                ]
                                            ],
                                            [
                                                [
                                                    "-1",
                                                    "0",
                                                    "0"
                                                ]
                                            ]
                                        ],
                                        "target": [
                                            "1/2"
                                        ]
                                    }
                                ]
                            }
                        ]
                    },
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
                                    "-1"
                                ]
                            ],
                            "vector": [
                                "0",
                                "0",
                                "0"
                            ],
                            "xyz": "-x,-y,-z",
                            "det": -1,
                            "is_orthogonal": true
                        },
                        "compatible_systems": [
                            "triclinic",
                            "monoclinic",
                            "orthorhombic",
                            "tetragonal",
                            "trigonal",
                            "hexagonal",
                            "cubic"
                        ],
                        "operation_kind": "affine"
                    }
                ]
            }
        }
    },
    "examples": [
        {
            "it_number": 1,
            "hall": "p_1",
            "affine_images": [
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
                        ]
                    }
                }
            ]
        }
    ]
}
```