# Workflow declaration URI (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/core/workflow_declaration_uri`](https://schemas.httk.org/defs/v0.1/properties/core/workflow_declaration_uri.md)**  
**Definition name:** `workflow_declaration_uri`

**Property name:** Workflow declaration URI  
**Description:** A URI identifying the workflow declaration (the reusable process definition, as opposed to a specific execution) behind a runs entry.
No particular URI scheme, resolvability, or formalism is mandated.
Providers wanting two runs recognized as executions of the same declaration MUST use an identical URI.
Null is expected for ad-hoc scripts, interactive executions, and legacy data with no formal workflow identifier.  
**Type:** string  
**Implementation requirements:**  
- **Support:** MUST be supported by all implementations, MUST NOT be `null`.  

- **Query:** MUST be a queryable property.  



**Examples:**

- `"https://github.com/httk-workflows/vasp-relax/releases/tag/v1.0.0"`
- `"https://schemas.httk.org/workflows/vasp-relax/v1.0"`

**Formats:** [[JSON](workflow_declaration_uri.json)] [[MD](workflow_declaration_uri.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/core/workflow_declaration_uri",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "Workflow declaration URI",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "workflow_declaration_uri",
        "label": "workflow_declaration_uri_property_httk"
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
    "description": "A URI identifying the workflow declaration (the reusable process definition, as opposed to a specific execution) behind a runs entry.\nNo particular URI scheme, resolvability, or formalism is mandated.\nProviders wanting two runs recognized as executions of the same declaration MUST use an identical URI.\nNull is expected for ad-hoc scripts, interactive executions, and legacy data with no formal workflow identifier.",
    "examples": [
        "https://github.com/httk-workflows/vasp-relax/releases/tag/v1.0.0",
        "https://schemas.httk.org/workflows/vasp-relax/v1.0"
    ]
}
```