# Time step (property)

This page documents an [OPTIMADE](https://www.optimade.org/) [Property Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/properties/trajectories/time_step`](https://schemas.httk.org/defs/v0.1/properties/trajectories/time_step.md)**  
**Definition name:** `time_step`

**Property name:** Time step  
**Description:** The molecular-dynamics integration time step between consecutive frames, in femtosecond (fs; 1 fs = 10^-15 s).
A `null` value indicates that the time step is unknown.  
**Type:** float  



**Examples:**



**Formats:** [[JSON](time_step.json)] [[MD](time_step.md)]

**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/properties/trajectories/time_step",
    "$schema": "https://schemas.optimade.org/meta/v1.3/optimade/property_definition.json",
    "title": "Time step",
    "x-optimade-type": "float",
    "x-optimade-definition": {
        "kind": "property",
        "version": "0.1.0",
        "format": "1.3",
        "name": "time_step",
        "label": "time_step_trajectories_httk"
    },
    "x-optimade-unit": "fs",
    "x-optimade-unit-definitions": [
        {
            "$id": "https://schemas.httk.org/defs/v0.1/units/si/general/femtosecond",
            "title": "femtosecond",
            "symbol": "fs",
            "display-symbol": "fs",
            "description": "A unit of time equal to 10^-15 seconds.",
            "x-optimade-definition": {
                "label": "femtosecond_si_general",
                "kind": "unit",
                "format": "1.2",
                "version": "0.1.0",
                "name": "femtosecond"
            }
        }
    ],
    "type": [
        "number",
        "null"
    ],
    "description": "The molecular-dynamics integration time step between consecutive frames, in femtosecond (fs; 1 fs = 10^-15 s).\nA `null` value indicates that the time step is unknown."
}
```