# source ID (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/core/source_id`](https://schemas.httk.org/defs/v0.1/properties/core/source_id.md)**  
**Definition name:** `source_id`

**Property name:** source ID  
**Description:** The run's identifier in the system that executed it. For httk-workflow jobs, this is the workspace and job identity in the form <workspace_id>:<job_id>. This property participates in httk content identity so re-collecting the same job deduplicates while distinct jobs remain distinct.  
**Type:** string  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**



**Formats:** [[JSON](source_id.json)] [[MD](source_id.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/core/source_id",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "source ID",
    "x-optimade-type": "string",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "source_id",
        "label": "source_id_property_httk"
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
    "description": "The run's identifier in the system that executed it. For httk-workflow jobs, this is the workspace and job identity in the form <workspace_id>:<job_id>. This property participates in httk content identity so re-collecting the same job deduplicates while distinct jobs remain distinct."
}
```