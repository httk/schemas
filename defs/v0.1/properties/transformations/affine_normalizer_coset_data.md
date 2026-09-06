# Affine normalizer coset data (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_coset_data`](https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_coset_data.md)**  
**Definition name:** `affine_normalizer_coset_data`

**Property name:** Affine normalizer coset data  
**Description:** Ordered table of bounded affine normalizer coset-representative data for crystallographic space groups, with one item for each Hall setting.  
**Type:** list  

The affine normalizer of a space group describes affine mappings that send the space group to itself.
In practical algorithms this information is useful after a candidate space-group setting has been identified, because additional normalizer representatives can be applied to explore equivalent descriptions, equivalent origin choices, or equivalent embeddings without changing the underlying space group.
The representatives are listed modulo the space group itself, so each listed operation represents an equivalence class of normalizer operations rather than every operation in that class.

The `orthogonal_affine_normalizer_cosets` list is the signed-permutation subset of representatives.
The `affine_normalizer_cosets` list is generated from a bounded set of unimodular integer linear parts and may include non-orthogonal representatives.
Both lists are finite bounded tables and MUST NOT be interpreted as complete infinite affine normalizers.
Each listed representative carries `compatible_systems`, which states the reference-setting metric families whose every tensor is preserved after transport to the actual Hall basis.

**Requirements/Conventions**:

- It MUST be a list of dictionaries.
- The list order MUST match the generator's Hall-setting order.
- The companion top-level `indicies.hall_symbol_to_affine_normalizer_coset_data` lookup maps normalized Hall entries to zero-based positions in this list; it is not an OPTIMADE property.
- Each dictionary MUST contain a `hall_entry` value equal to the Hall-entry key used by the companion index.
- `n_cosets` MUST equal the length of `affine_normalizer_cosets`, and `n_orthogonal_cosets` MUST equal the length of `orthogonal_affine_normalizer_cosets`.
- The counts inside `candidate_sets` describe earlier search stages, whose full candidate lists are not stored, rather than the lengths of the final representative lists.
- Matrix and vector entries inside representatives MUST be exact strings, using integer strings or fraction strings as appropriate.
- The `candidate_sets` dictionary records generation bookkeeping for the finite candidate searches and is not itself a crystallographic normalizer object.

For the infinite space group G, an affine map A normalizes G when `A*G*A^-1 = G`, including its full translation lattice.
Representatives differing by multiplication by an element of G describe the same coset.
The identity coset G itself is omitted, but a nonzero pure translation can represent a nontrivial coset and MUST NOT be discarded just because its matrix is identity.
Continuous origin shifts are represented separately by `continuous_normalizer`; this finite list is not all of `N_A(G)/G`.
A nonempty `compatible_systems` list means the linear part preserves every metric in at least one listed reference-setting family after transport to the recorded Hall basis.
It need not preserve the actual setting's general metric; that distinction is recorded by `affine_transformation.is_orthogonal`.
The signed-permutation candidate set is contained in the bounded integer candidate set, but independently chosen coset representatives need not appear as identical affine matrices and vectors in both lists.

**Examples:**

- `[{"hall_entry": "-p_4_2_3", "it_number": 221, "crystal_system": "cubic", "orthogonal_affine_normalizer_cosets": [{"compatible_systems": ["triclinic", "monoclinic", "orthorhombic", "tetragonal", "trigonal", "hexagonal", "cubic"], "affine_transformation": {"matrix": [["-1", "0", "0"], ["0", "-1", "0"], ["0", "0", "-1"]], "vector": ["1/2", "1/2", "1/2"], "xyz": "-x+1/2,-y+1/2,-z+1/2", "det": -1, "is_orthogonal": true}}], "affine_normalizer_cosets": [{"compatible_systems": ["triclinic", "monoclinic", "orthorhombic", "tetragonal", "trigonal", "hexagonal", "cubic"], "affine_transformation": {"matrix": [["-1", "0", "0"], ["0", "-1", "0"], ["0", "0", "-1"]], "vector": ["1/2", "1/2", "1/2"], "xyz": "-x+1/2,-y+1/2,-z+1/2", "det": -1, "is_orthogonal": true}}], "n_orthogonal_cosets": 1, "n_cosets": 1, "candidate_sets": {"orthogonal_affine_normalizer_cosets": {"candidate_set": "signed_permutation_matrices", "n_linear_candidates": 48, "n_raw_candidates": 96, "n_coset_representatives_before_metric_filter": 1}, "affine_normalizer_cosets": {"candidate_set": "bounded_unimodular_integer_matrices", "n_linear_candidates": 6960, "n_raw_candidates": 96, "n_coset_representatives_before_metric_filter": 1, "bounds": {"det_abs": 1, "max_abs_linear_entry": 1}}}}]`

**Formats:** [[JSON](affine_normalizer_coset_data.json)] [[MD](affine_normalizer_coset_data.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_coset_data",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Affine normalizer coset data",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "affine_normalizer_coset_data",
        "label": "affine_normalizer_coset_data_transformations"
    },
    "x-optimade-unit": "inapplicable",
    "type": [
        "array",
        "null"
    ],
    "description": "Ordered table of bounded affine normalizer coset-representative data for crystallographic space groups, with one item for each Hall setting.\n\nThe affine normalizer of a space group describes affine mappings that send the space group to itself.\nIn practical algorithms this information is useful after a candidate space-group setting has been identified, because additional normalizer representatives can be applied to explore equivalent descriptions, equivalent origin choices, or equivalent embeddings without changing the underlying space group.\nThe representatives are listed modulo the space group itself, so each listed operation represents an equivalence class of normalizer operations rather than every operation in that class.\n\nThe `orthogonal_affine_normalizer_cosets` list is the signed-permutation subset of representatives.\nThe `affine_normalizer_cosets` list is generated from a bounded set of unimodular integer linear parts and may include non-orthogonal representatives.\nBoth lists are finite bounded tables and MUST NOT be interpreted as complete infinite affine normalizers.\nEach listed representative carries `compatible_systems`, which states the reference-setting metric families whose every tensor is preserved after transport to the actual Hall basis.\n\n**Requirements/Conventions**:\n\n- It MUST be a list of dictionaries.\n- The list order MUST match the generator's Hall-setting order.\n- The companion top-level `indicies.hall_symbol_to_affine_normalizer_coset_data` lookup maps normalized Hall entries to zero-based positions in this list; it is not an OPTIMADE property.\n- Each dictionary MUST contain a `hall_entry` value equal to the Hall-entry key used by the companion index.\n- `n_cosets` MUST equal the length of `affine_normalizer_cosets`, and `n_orthogonal_cosets` MUST equal the length of `orthogonal_affine_normalizer_cosets`.\n- The counts inside `candidate_sets` describe earlier search stages, whose full candidate lists are not stored, rather than the lengths of the final representative lists.\n- Matrix and vector entries inside representatives MUST be exact strings, using integer strings or fraction strings as appropriate.\n- The `candidate_sets` dictionary records generation bookkeeping for the finite candidate searches and is not itself a crystallographic normalizer object.\n\nFor the infinite space group G, an affine map A normalizes G when `A*G*A^-1 = G`, including its full translation lattice.\nRepresentatives differing by multiplication by an element of G describe the same coset.\nThe identity coset G itself is omitted, but a nonzero pure translation can represent a nontrivial coset and MUST NOT be discarded just because its matrix is identity.\nContinuous origin shifts are represented separately by `continuous_normalizer`; this finite list is not all of `N_A(G)/G`.\nA nonempty `compatible_systems` list means the linear part preserves every metric in at least one listed reference-setting family after transport to the recorded Hall basis.\nIt need not preserve the actual setting's general metric; that distinction is recorded by `affine_transformation.is_orthogonal`.\nThe signed-permutation candidate set is contained in the bounded integer candidate set, but independently chosen coset representatives need not appear as identical affine matrices and vectors in both lists.",
    "items": {
        "x-optimade-type": "dictionary",
        "x-optimade-unit": "inapplicable",
        "type": [
            "object",
            "null"
        ],
        "description": "One affine-normalizer coset-data row for a single Hall setting.\n\n**Requirements/Conventions**:\n\n- It MUST be a dictionary with the following keys:\n\n    - **hall\\_entry**: REQUIRED; String.\n      Normalized Hall entry identifying the Hall setting represented by this row.\n\n    - **it\\_number**: REQUIRED; Integer.\n      International Tables space-group number of the represented Hall setting.\n\n    - **crystal\\_system**: REQUIRED; String.\n      Crystal system of the represented Hall setting.\n\n    - **orthogonal\\_affine\\_normalizer\\_cosets**: REQUIRED; List of dictionaries.\n      Signed-permutation affine normalizer coset representatives modulo the space group.\n      Each item follows `/defs/v0.1/properties/symmetry/basis_transform`.\n\n    - **affine\\_normalizer\\_cosets**: REQUIRED; List of dictionaries.\n      Bounded affine normalizer coset representatives modulo the space group.\n      Each item follows `/defs/v0.1/properties/symmetry/basis_transform`.\n\n    - **n\\_orthogonal\\_cosets**: REQUIRED; Integer.\n      Number of representatives in `orthogonal_affine_normalizer_cosets`.\n\n    - **n\\_cosets**: REQUIRED; Integer.\n      Number of representatives in `affine_normalizer_cosets`.\n\n    - **candidate\\_sets**: REQUIRED; Dictionary.\n      Generator bookkeeping for the finite candidate sets used to produce the two representative lists.",
        "properties": {
            "hall_entry": {
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
            "crystal_system": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/pointgroups/crystal_system",
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
            "orthogonal_affine_normalizer_cosets": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/orthogonal_affine_normalizer_cosets",
                "title": "Orthogonal affine normalizer cosets",
                "x-optimade-type": "list",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "orthogonal_affine_normalizer_cosets",
                    "label": "orthogonal_affine_normalizer_cosets_transformations"
                },
                "x-optimade-unit": "inapplicable",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Runtime list of orthogonal signed-permutation affine normalizer coset representatives modulo the space group.\n\nEach item is one finite listed representative and follows `/defs/v0.1/properties/symmetry/basis_transform`.\nThe list is a bounded representative table, not a complete infinite affine normalizer.\n\nThe identity coset is excluded; discrete origin-shift cosets with identity linear part can still occur.\nThe exact coordinate action is `x_out = matrix*x_in + vector` in the recorded Hall setting.\nFor the normalization condition, metric annotations, and search scope, see `/defs/v0.1/properties/transformations/affine_normalizer_coset_data`.",
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
                },
                "examples": [
                    [
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
                            }
                        }
                    ]
                ]
            },
            "affine_normalizer_cosets": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/affine_normalizer_cosets",
                "title": "Affine normalizer cosets",
                "x-optimade-type": "list",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "affine_normalizer_cosets",
                    "label": "affine_normalizer_cosets_transformations"
                },
                "x-optimade-unit": "inapplicable",
                "type": [
                    "array",
                    "null"
                ],
                "description": "Runtime list of bounded affine normalizer coset representatives modulo the space group.\n\nEach item is one finite listed representative and follows `/defs/v0.1/properties/symmetry/basis_transform`.\nThe list is a bounded representative table, not a complete infinite affine normalizer.\n\nThe identity coset is excluded; discrete origin-shift cosets with identity linear part can still occur.\nThe exact coordinate action is `x_out = matrix*x_in + vector` in the recorded Hall setting.\nFor the normalization condition, metric annotations, and search scope, see `/defs/v0.1/properties/transformations/affine_normalizer_coset_data`.",
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
                },
                "examples": [
                    [
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
                            }
                        }
                    ]
                ]
            },
            "n_orthogonal_cosets": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/n_orthogonal_cosets",
                "title": "Number of orthogonal cosets",
                "x-optimade-type": "integer",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "n_orthogonal_cosets",
                    "label": "n_orthogonal_cosets_transformations"
                },
                "type": [
                    "integer",
                    "null"
                ],
                "description": "Number of orthogonal affine normalizer coset representatives stored for the setting.\n\nThis value MUST equal the length of the `orthogonal_affine_normalizer_cosets` list of the containing record.\n\nThe trivial space-group coset is excluded; the count is for the bounded, metric-filtered list and is not the cardinality of the full affine-normalizer quotient.",
                "x-optimade-unit": "inapplicable",
                "examples": [
                    47,
                    23
                ]
            },
            "n_cosets": {
                "$id": "https://schemas.httk.org/defs/v0.1/properties/transformations/n_cosets",
                "title": "Number of cosets",
                "x-optimade-type": "integer",
                "x-optimade-definition": {
                    "kind": "property",
                    "version": "0.1.0",
                    "format": "1.3",
                    "name": "n_cosets",
                    "label": "n_cosets_transformations"
                },
                "type": [
                    "integer",
                    "null"
                ],
                "description": "Number of affine normalizer coset representatives stored for the setting.\n\nThis value MUST equal the length of the `affine_normalizer_cosets` list of the containing record.\n\nThe trivial space-group coset is excluded; the count is for the bounded, metric-filtered list and is not the cardinality of the full affine-normalizer quotient.",
                "x-optimade-unit": "inapplicable",
                "examples": [
                    63,
                    31
                ]
            },
            "candidate_sets": {
                "x-optimade-type": "dictionary",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "object",
                    "null"
                ],
                "description": "Generator bookkeeping for the finite candidate sets used to produce the stored affine-normalizer coset representatives.\nThis dictionary records how many candidate affine operations were considered before and after quotienting modulo the space group and before applying metric-compatibility filters.",
                "properties": {
                    "orthogonal_affine_normalizer_cosets": {
                        "x-optimade-type": "dictionary",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "object",
                            "null"
                        ],
                        "description": "Candidate-set metadata for the orthogonal signed-permutation representative list.",
                        "properties": {
                            "candidate_set": {
                                "x-optimade-type": "string",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "string",
                                    "null"
                                ],
                                "description": "Name of the linear candidate set used by the generator."
                            },
                            "n_linear_candidates": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Number of linear matrices in the raw candidate set."
                            },
                            "n_raw_candidates": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Number of affine candidates generated before deduplication modulo the space group."
                            },
                            "n_coset_representatives_before_metric_filter": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Number of coset representatives before filtering by crystal metric compatibility."
                            }
                        }
                    },
                    "affine_normalizer_cosets": {
                        "x-optimade-type": "dictionary",
                        "x-optimade-unit": "inapplicable",
                        "type": [
                            "object",
                            "null"
                        ],
                        "description": "Candidate-set metadata for the bounded unimodular-integer representative list.",
                        "properties": {
                            "candidate_set": {
                                "x-optimade-type": "string",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "string",
                                    "null"
                                ],
                                "description": "Name of the linear candidate set used by the generator."
                            },
                            "n_linear_candidates": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Number of linear matrices in the raw candidate set."
                            },
                            "n_raw_candidates": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Number of affine candidates generated before deduplication modulo the space group."
                            },
                            "n_coset_representatives_before_metric_filter": {
                                "x-optimade-type": "integer",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "integer",
                                    "null"
                                ],
                                "description": "Number of coset representatives before filtering by crystal metric compatibility."
                            },
                            "bounds": {
                                "x-optimade-type": "dictionary",
                                "x-optimade-unit": "inapplicable",
                                "type": [
                                    "object",
                                    "null"
                                ],
                                "description": "Bounds that define the finite bounded unimodular-integer linear candidate set.",
                                "properties": {
                                    "det_abs": {
                                        "x-optimade-type": "integer",
                                        "x-optimade-unit": "inapplicable",
                                        "type": [
                                            "integer",
                                            "null"
                                        ],
                                        "description": "Required absolute determinant of every bounded linear candidate."
                                    },
                                    "max_abs_linear_entry": {
                                        "x-optimade-type": "integer",
                                        "x-optimade-unit": "inapplicable",
                                        "type": [
                                            "integer",
                                            "null"
                                        ],
                                        "description": "Maximum absolute value allowed for entries of the bounded integer linear candidates."
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
        [
            {
                "hall_entry": "-p_4_2_3",
                "it_number": 221,
                "crystal_system": "cubic",
                "orthogonal_affine_normalizer_cosets": [
                    {
                        "compatible_systems": [
                            "triclinic",
                            "monoclinic",
                            "orthorhombic",
                            "tetragonal",
                            "trigonal",
                            "hexagonal",
                            "cubic"
                        ],
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
                                "1/2",
                                "1/2",
                                "1/2"
                            ],
                            "xyz": "-x+1/2,-y+1/2,-z+1/2",
                            "det": -1,
                            "is_orthogonal": true
                        }
                    }
                ],
                "affine_normalizer_cosets": [
                    {
                        "compatible_systems": [
                            "triclinic",
                            "monoclinic",
                            "orthorhombic",
                            "tetragonal",
                            "trigonal",
                            "hexagonal",
                            "cubic"
                        ],
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
                                "1/2",
                                "1/2",
                                "1/2"
                            ],
                            "xyz": "-x+1/2,-y+1/2,-z+1/2",
                            "det": -1,
                            "is_orthogonal": true
                        }
                    }
                ],
                "n_orthogonal_cosets": 1,
                "n_cosets": 1,
                "candidate_sets": {
                    "orthogonal_affine_normalizer_cosets": {
                        "candidate_set": "signed_permutation_matrices",
                        "n_linear_candidates": 48,
                        "n_raw_candidates": 96,
                        "n_coset_representatives_before_metric_filter": 1
                    },
                    "affine_normalizer_cosets": {
                        "candidate_set": "bounded_unimodular_integer_matrices",
                        "n_linear_candidates": 6960,
                        "n_raw_candidates": 96,
                        "n_coset_representatives_before_metric_filter": 1,
                        "bounds": {
                            "det_abs": 1,
                            "max_abs_linear_entry": 1
                        }
                    }
                }
            }
        ]
    ]
}
```