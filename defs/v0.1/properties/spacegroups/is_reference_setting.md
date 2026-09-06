# is reference setting (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_reference_setting`](https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_reference_setting.md)**  
**Definition name:** `is_reference_setting`

**Property name:** is reference setting  
**Description:** Whether cctbx identifies this Hall setting as its reference setting for the space-group type.
This is the reference used by cctbx's change-of-basis machinery; it must not be inferred solely from the setting-specific Hermann-Mauguin symbol.
For the pipeline's selected IT-standard setting, use `index_it_number_to_std_spacegroups` in the dataset's companion `indicies` structure.  
**Type:** boolean  



**Examples:**

- `true`
- `false`

**Formats:** [[JSON](is_reference_setting.json)] [[MD](is_reference_setting.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/spacegroups/is_reference_setting",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "is reference setting",
    "x-optimade-type": "boolean",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "is_reference_setting",
        "label": "is_reference_setting_spacegroups"
    },
    "type": [
        "boolean",
        "null"
    ],
    "description": "Whether cctbx identifies this Hall setting as its reference setting for the space-group type.\nThis is the reference used by cctbx's change-of-basis machinery; it must not be inferred solely from the setting-specific Hermann-Mauguin symbol.\nFor the pipeline's selected IT-standard setting, use `index_it_number_to_std_spacegroups` in the dataset's companion `indicies` structure.",
    "x-optimade-unit": "inapplicable",
    "examples": [
        true,
        false
    ]
}
```