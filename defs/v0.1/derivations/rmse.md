Root-mean-square error
----------------------


``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/derivations/rmse",
    "title": "Root-mean-square error",
    "description": "The root-mean-square of the signed residuals of the base property, predicted minus reference unless stated otherwise.\nThe derivation term applies to a base property definition identified alongside; the value has the base property's unit and shape.",
    "x-httk-definition": {
        "kind": "derivation",
        "format": "0.1",
        "version": "0.1.0",
        "name": "rmse",
        "label": "rmse_derivation_httk"
    },
    "unit-rule": "same-as-base",
    "shape-rule": "same-as-base"
}
```