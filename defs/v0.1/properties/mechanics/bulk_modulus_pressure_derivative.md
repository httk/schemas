# Bulk modulus pressure derivative (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_pressure_derivative`](https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_pressure_derivative.md)**  
**Definition name:** `bulk_modulus_pressure_derivative`

**Property name:** Bulk modulus pressure derivative  
**Description:** The pressure derivative of the bulk modulus, B' = dB/dP at the reference state (dimensionless).
A null value means the quantity is not available or not recorded.  
**Type:** float  
**Implementation requirements:**  
- **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.  

- **Query:** MUST be a queryable property with support for all mandatory filter features.  



**Examples:**



**Formats:** [[JSON](bulk_modulus_pressure_derivative.json)] [[MD](bulk_modulus_pressure_derivative.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/mechanics/bulk_modulus_pressure_derivative",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Bulk modulus pressure derivative",
    "x-optimade-type": "float",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "bulk_modulus_pressure_derivative",
        "label": "bulk_modulus_pressure_derivative_mechanics_httk"
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
    "description": "The pressure derivative of the bulk modulus, B' = dB/dP at the reference state (dimensionless).\nA null value means the quantity is not available or not recorded."
}
```