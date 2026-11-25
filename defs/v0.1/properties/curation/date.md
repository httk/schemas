# note date (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/curation/date`](https://schemas.httk.org/defs/v0.1/properties/curation/date.md)**  
**Definition name:** `date`

**Property name:** note date  
**Description:** When the note was made, as a timezone-aware timestamp chosen by the note's source. This is not the time the note was stored.  
**Type:** timestamp  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  
- **Response:**  



**Examples:**

- `"2007-04-05T14:30:20Z"`

**Formats:** [[JSON](date.json)] [[MD](date.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/date",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/property_definition.json",
    "title": "note date",
    "x-optimade-type": "timestamp",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "date",
        "label": "date_property_httk"
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
    "description": "When the note was made, as a timezone-aware timestamp chosen by the note's source. This is not the time the note was stored.",
    "examples": [
        "2007-04-05T14:30:20Z"
    ]
}
```