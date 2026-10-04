# Universal anisotropy index (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/mechanics/universal_anisotropy_index`](https://schemas.httk.org/defs/v0.1/properties/mechanics/universal_anisotropy_index.md)**  
**Definition name:** `universal_anisotropy_index`

**Property name:** Universal anisotropy index  
**Description:** The universal elastic anisotropy index A^U = 5 G_V/G_R + K_V/K_R - 6 (dimensionless); zero for an elastically isotropic crystal.
A null value means the quantity is not available or not recorded.  
**Type:** float  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  



**Examples:**



**Formats:** [[JSON](universal_anisotropy_index.json)] [[MD](universal_anisotropy_index.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/mechanics/universal_anisotropy_index",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Universal anisotropy index",
    "x-optimade-type": "float",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "universal_anisotropy_index",
        "label": "universal_anisotropy_index_mechanics_httk"
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
    "description": "The universal elastic anisotropy index A^U = 5 G_V/G_R + K_V/K_R - 6 (dimensionless); zero for an elastically isotropic crystal.\nA null value means the quantity is not available or not recorded."
}
```