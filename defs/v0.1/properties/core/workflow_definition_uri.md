# Workflow definition URI (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/core/workflow_definition_uri`](https://schemas.httk.org/defs/v0.1/properties/core/workflow_definition_uri.md)**  
**Definition name:** `workflow_definition_uri`

**Property name:** Workflow definition URI  
**Description:** A URI identifying the workflow definition (the code that ran) behind a runs entry, as opposed to the workflow declaration identified by `workflow_declaration_uri`.
A typical value is a git URI pinned to a full commit hash, of the form `git+https://host/path@<commit>#<subdir>`.
No particular URI scheme or resolvability is mandated, but providers SHOULD use a URI that pins the exact code revision.
Null is expected when the executed code is unknown, e.g., for legacy data.  
**Type:** string  
**Implementation requirements:**  
- **Support:** MUST be supported by all implementations, MUST NOT be `null`.  

- **Query:** MUST be a queryable property.  



**Examples:**

- `"git+https://github.com/httk/workflows-vasp@458aacb2493586faa2c9ac033334457569aeaf75#vasp-relax"`

**Formats:** [[JSON](workflow_definition_uri.json)] [[MD](workflow_definition_uri.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/core/workflow_definition_uri",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "Workflow definition URI",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "workflow_definition_uri",
        "label": "workflow_definition_uri_property_httk"
    },
    "x-optimade-unit": "inapplicable",
    "x-optimade-requirements": {
        "support": "must",
        "sortable": false,
        "query-support": "partial",
        "query-support-operators": [
            "=",
            "!="
        ]
    },
    "type": [
        "string",
        "null"
    ],
    "description": "A URI identifying the workflow definition (the code that ran) behind a runs entry, as opposed to the workflow declaration identified by `workflow_declaration_uri`.\nA typical value is a git URI pinned to a full commit hash, of the form `git+https://host/path@<commit>#<subdir>`.\nNo particular URI scheme or resolvability is mandated, but providers SHOULD use a URI that pins the exact code revision.\nNull is expected when the executed code is unknown, e.g., for legacy data.",
    "examples": [
        "git+https://github.com/httk/workflows-vasp@458aacb2493586faa2c9ac033334457569aeaf75#vasp-relax"
    ]
}
```