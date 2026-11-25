# import reports (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/imports/reports`](https://schemas.httk.org/defs/v0.1/properties/imports/reports.md)**  
**Definition name:** `reports`

**Property name:** import reports  
**Description:** The diagnostics (warnings, notices, and exceptions) reported while importing the thing, in emission order.  
**Type:** list  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** Support for queries on this property is OPTIONAL.  
- **Response:**  

**Requirements/Conventions**:

- It MUST be a list of dictionaries.
- `level` is the lowercase logging level name of the report, e.g. "warning".
- `message` is the report message.
- `context` is the report context tag, e.g. "cif", or null when the report has none.
- `logger` is the name of the logger that emitted the report, or null when unknown.

**Examples:**

- `[{"level": "warning", "message": "Dropped an auxiliary loop to make the CIF parsable.", "context": "cif", "logger": "httk.atomistic.io.cif"}]`

**Formats:** [[JSON](reports.json)] [[MD](reports.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/imports/reports",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "import reports",
    "x-optimade-type": "list",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "reports",
        "label": "reports_property_httk"
    },
    "x-optimade-dimensions": {
        "names": [
            "dim_import_reports"
        ],
        "sizes": [
            null
        ]
    },
    "x-optimade-unit": "inapplicable",
    "x-optimade-requirements": {
        "support": "may",
        "sortable": false,
        "query-support": "none",
        "response-level": "may"
    },
    "type": [
        "array",
        "null"
    ],
    "description": "The diagnostics (warnings, notices, and exceptions) reported while importing the thing, in emission order.\n\n**Requirements/Conventions**:\n\n- It MUST be a list of dictionaries.\n- `level` is the lowercase logging level name of the report, e.g. \"warning\".\n- `message` is the report message.\n- `context` is the report context tag, e.g. \"cif\", or null when the report has none.\n- `logger` is the name of the logger that emitted the report, or null when unknown.",
    "items": {
        "title": "import report",
        "x-optimade-type": "dictionary",
        "x-optimade-unit": "inapplicable",
        "type": [
            "object"
        ],
        "description": "One diagnostic reported while importing the thing.",
        "properties": {
            "level": {
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "string"
                ],
                "description": "The lowercase logging level name of the report, e.g. \"warning\"."
            },
            "message": {
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "string"
                ],
                "description": "The report message."
            },
            "context": {
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "string",
                    "null"
                ],
                "description": "The report context tag, e.g. \"cif\"; null when the report has none."
            },
            "logger": {
                "x-optimade-type": "string",
                "x-optimade-unit": "inapplicable",
                "type": [
                    "string",
                    "null"
                ],
                "description": "The name of the logger that emitted the report; null when unknown."
            }
        },
        "required": [
            "level",
            "message",
            "context",
            "logger"
        ]
    },
    "examples": [
        [
            {
                "level": "warning",
                "message": "Dropped an auxiliary loop to make the CIF parsable.",
                "context": "cif",
                "logger": "httk.atomistic.io.cif"
            }
        ]
    ]
}
```