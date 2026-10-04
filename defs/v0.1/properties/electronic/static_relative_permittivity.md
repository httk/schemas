# Static relative permittivity (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/electronic/static_relative_permittivity`](https://schemas.httk.org/defs/v0.1/properties/electronic/static_relative_permittivity.md)**  
**Definition name:** `static_relative_permittivity`

**Property name:** Static relative permittivity  
**Description:** The static relative permittivity (dielectric constant), dimensionless, as the isotropic mean (trace/3) of the static relative-permittivity tensor, which includes both the ionic and the electronic contributions.
A null value means the quantity is not available or not recorded.  
**Type:** float  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  



**Examples:**



**Formats:** [[JSON](static_relative_permittivity.json)] [[MD](static_relative_permittivity.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/electronic/static_relative_permittivity",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Static relative permittivity",
    "x-optimade-type": "float",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "static_relative_permittivity",
        "label": "static_relative_permittivity_electronic_httk"
    },
    "x-optimade-unit": "dimensionless",
    "x-optimade-requirements": {
        "support": "may",
        "sortable": false,
        "query-support": "all mandatory"
    },
    "type": [
        "number",
        "null"
    ],
    "description": "The static relative permittivity (dielectric constant), dimensionless, as the isotropic mean (trace/3) of the static relative-permittivity tensor, which includes both the ionic and the electronic contributions.\nA null value means the quantity is not available or not recorded."
}
```