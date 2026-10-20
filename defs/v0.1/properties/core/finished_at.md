# run finish time (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/core/finished_at`](https://schemas.httk.org/defs/v0.1/properties/core/finished_at.md)**  
**Definition name:** `finished_at`

**Property name:** run finish time  
**Description:** When the run finished: for httk-workflow jobs, the end of the last attempt of the job, as a timezone-aware timestamp.  
**Type:** timestamp  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**

- `"2007-04-05T14:30:20Z"`

**Formats:** [[JSON](finished_at.json)] [[MD](finished_at.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/core/finished_at",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "run finish time",
    "x-optimade-type": "timestamp",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "finished_at",
        "label": "finished_at_property_httk"
    },
    "x-optimade-unit": "inapplicable",
    "x-optimade-requirements": {
        "support": "may",
        "sortable": true,
        "query-support": "all mandatory",
        "response-level": "may"
    },
    "type": [
        "string",
        "null"
    ],
    "format": "date-time",
    "description": "When the run finished: for httk-workflow jobs, the end of the last attempt of the job, as a timezone-aware timestamp.",
    "examples": [
        "2007-04-05T14:30:20Z"
    ]
}
```