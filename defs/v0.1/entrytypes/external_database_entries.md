# httk external database entries entry type (entrytype)

This page documents an [OPTIMADE](https://www.optimade.org/) [Entrytype Definition](https://schemas.optimade.org/#definitions). See [https://schemas.optimade.org/](https://schemas.optimade.org/) for more information.

**ID: [`https://schemas.httk.org/defs/v0.1/entrytypes/external_database_entries`](https://schemas.httk.org/defs/v0.1/entrytypes/external_database_entries.md)**  
**Definition name:** `external_database_entries`

**Entrytype name:** httk external database entries entry type  
**Description:** An external_database_entries entry identifies one entry of an external database that other entries link to.
The reference describing the whole external database is linked to it through its references relationship.  

**Formats:** [[JSON](external_database_entries.json)] [[MD](external_database_entries.md)]

This entrytype defines the following properties:

* **[ID](https://schemas.optimade.org/defs/v1.2/properties/core/id.md)** (property) - [`https://schemas.optimade.org/defs/v1.2/properties/core/id`](https://schemas.optimade.org/defs/v1.2/properties/core/id.md)  
  A unique string referencing a specific entry in the database.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST always be included in the response.
    - Taken together, the ID and entry type MUST uniquely identify the entry.
    - Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.
    - IDs MAY change over time.


* **[type](https://schemas.optimade.org/defs/v1.2/properties/core/type.md)** (property) - [`https://schemas.optimade.org/defs/v1.2/properties/core/type`](https://schemas.optimade.org/defs/v1.2/properties/core/type.md)  
  The name of the type of an entry.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST always be included in the response.
    - MUST be an existing entry type.
    - The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.


* **[immutable ID (immutable_id)](https://schemas.optimade.org/defs/v1.2/properties/core/immutable_id.md)** (property) - [`https://schemas.optimade.org/defs/v1.2/properties/core/immutable_id`](https://schemas.optimade.org/defs/v1.2/properties/core/immutable_id.md)  
  The entry's immutable ID (e.g., a UUID).

    **Requirements/Conventions:**  

    - **Support:** OPTIONAL support in implementations, i.e., MAY be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MAY be included by default in the response.
    - This is important for databases having preferred IDs that point to "the latest version" of a record, but still offer access to older variants.
    - This ID maps to the version-specific record, in case it changes in the future.


* **[last modified (last_modified)](https://schemas.optimade.org/defs/v1.2/properties/core/last_modified.md)** (property) - [`https://schemas.optimade.org/defs/v1.2/properties/core/last_modified`](https://schemas.optimade.org/defs/v1.2/properties/core/last_modified.md)  
  Date and time representing when the entry was last modified.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[external database provider (database_provider)](../properties/curation/database_provider.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/curation/database_provider`](https://schemas.httk.org/defs/v0.1/properties/curation/database_provider.md)  
  The provider of the external database. This is the OPTIMADE provider prefix, as registered in the OPTIMADE providers list, e.g. "cod", "oqmd", or "mp", and an equivalent short lowercase name when no registered prefix exists.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[external database (database)](../properties/curation/database.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/curation/database`](https://schemas.httk.org/defs/v0.1/properties/curation/database.md)  
  The specific database, of the provider given by database_provider, that the entry belongs to, as a short identifier. Null means the provider's only or main database.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[external entry ID (entry_id)](../properties/curation/entry_id.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/curation/entry_id`](https://schemas.httk.org/defs/v0.1/properties/curation/entry_id.md)  
  The identifier of the entry in the external database, as that database writes it.

    **Requirements/Conventions:**  

    - **Support:** MUST be supported by all implementations, MUST NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[external entry URL (url)](../properties/curation/url.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/curation/url`](https://schemas.httk.org/defs/v0.1/properties/curation/url.md)  
  A URL of the entry in the external database, if available.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.

* **[external entry role (role)](../properties/curation/role.md)** (property) - [`https://schemas.httk.org/defs/v0.1/properties/curation/role`](https://schemas.httk.org/defs/v0.1/properties/curation/role.md)  
  How the linking entry relates to the external entry: null for a general relation, and "origin" when the linking entry was obtained from the external entry.

    **Requirements/Conventions:**  

    - **Support:** SHOULD be supported by all implementations, i.e., SHOULD NOT be `null`.
    - **Query:** MUST be a queryable property with support for all mandatory filter features.
    - **Response:** MUST be included by default in the response.


**JSON definition:**

``` json
{
    "$id": "https://schemas.httk.org/defs/v0.1/entrytypes/external_database_entries",
    "$schema": "https://schemas.optimade.org/meta/v1.2/optimade/entrytype_definition.json",
    "type": "object",
    "title": "httk external database entries entry type",
    "x-optimade-definition": {
        "kind": "entrytype",
        "format": "1.3",
        "version": "0.1.0",
        "name": "external_database_entries",
        "label": "external_database_entries_entrytype_httk"
    },
    "description": "An external_database_entries entry identifies one entry of an external database that other entries link to.\nThe reference describing the whole external database is linked to it through its references relationship.",
    "properties": {
        "id": {
            "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/id",
            "x-optimade-requirements": {
                "support": "must",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "always"
            },
            "title": "ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "label": "id_core",
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "id"
            },
            "type": [
                "string"
            ],
            "description": "A unique string referencing a specific entry in the database.\n\n**Requirements/Conventions:**\n\n- Taken together, the ID and entry type MUST uniquely identify the entry.\n- Reasonably short IDs are encouraged and SHOULD NOT be longer than 255 characters.\n- IDs MAY change over time.",
            "examples": [
                "db/1234567",
                "cod/2000000",
                "cod/2000000@1234567",
                "nomad/L1234567890",
                "42"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "type": {
            "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/type",
            "x-optimade-requirements": {
                "support": "must",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "always"
            },
            "title": "type",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "label": "type_core",
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "type"
            },
            "type": [
                "string"
            ],
            "description": "The name of the type of an entry.\n\n**Requirements/Conventions:**\n\n- MUST be an existing entry type.\n- The entry of type <type> and ID <id> MUST be returned in response to a request for /<type>/<id> under the versioned or unversioned base URL serving the API.",
            "examples": [
                "structures"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "immutable_id": {
            "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/immutable_id",
            "x-optimade-requirements": {
                "support": "may",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "may"
            },
            "title": "immutable ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "label": "immutable_id_core",
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "immutable_id"
            },
            "type": [
                "string",
                "null"
            ],
            "description": "The entry's immutable ID (e.g., a UUID).\n\n**Requirements/Conventions:**\n\n- This is important for databases having preferred IDs that point to \"the latest version\" of a record, but still offer access to older variants.\n- This ID maps to the version-specific record, in case it changes in the future.",
            "examples": [
                "8bd3e750-b477-41a0-9b11-3a799f21b44f",
                "fjeiwoj,54;@=%<>#32"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "last_modified": {
            "$id": "https://schemas.optimade.org/defs/v1.2/properties/core/last_modified",
            "x-optimade-requirements": {
                "support": "should",
                "sortable": false,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "title": "last modified",
            "x-optimade-type": "timestamp",
            "x-optimade-definition": {
                "label": "last_modified_core",
                "kind": "property",
                "version": "1.2.0",
                "format": "1.2",
                "name": "last_modified"
            },
            "type": [
                "string",
                "null"
            ],
            "format": "date-time",
            "description": "Date and time representing when the entry was last modified.",
            "examples": [
                "2007-04-05T14:30:20Z"
            ],
            "x-optimade-unit": "inapplicable"
        },
        "database_provider": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/database_provider",
            "x-optimade-requirements": {
                "support": "must",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "title": "external database provider",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "database_provider",
                "label": "database_provider_property_httk"
            },
            "x-optimade-unit": "inapplicable",
            "type": [
                "string",
                "null"
            ],
            "description": "The provider of the external database. This is the OPTIMADE provider prefix, as registered in the OPTIMADE providers list, e.g. \"cod\", \"oqmd\", or \"mp\", and an equivalent short lowercase name when no registered prefix exists."
        },
        "database": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/database",
            "x-optimade-requirements": {
                "support": "should",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "title": "external database",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "database",
                "label": "database_property_httk"
            },
            "x-optimade-unit": "inapplicable",
            "type": [
                "string",
                "null"
            ],
            "description": "The specific database, of the provider given by database_provider, that the entry belongs to, as a short identifier. Null means the provider's only or main database."
        },
        "entry_id": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/entry_id",
            "x-optimade-requirements": {
                "support": "must",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "title": "external entry ID",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "entry_id",
                "label": "entry_id_property_httk"
            },
            "x-optimade-unit": "inapplicable",
            "type": [
                "string",
                "null"
            ],
            "description": "The identifier of the entry in the external database, as that database writes it."
        },
        "url": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/url",
            "x-optimade-requirements": {
                "support": "should",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "title": "external entry URL",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "url",
                "label": "url_property_httk"
            },
            "x-optimade-unit": "inapplicable",
            "type": [
                "string",
                "null"
            ],
            "description": "A URL of the entry in the external database, if available."
        },
        "role": {
            "$id": "https://schemas.httk.org/defs/v0.1/properties/curation/role",
            "x-optimade-requirements": {
                "support": "should",
                "sortable": true,
                "query-support": "all mandatory",
                "response-level": "must"
            },
            "title": "external entry role",
            "x-optimade-type": "string",
            "x-optimade-definition": {
                "kind": "property",
                "version": "0.1.0",
                "format": "1.3",
                "name": "role",
                "label": "role_property_httk"
            },
            "x-optimade-unit": "inapplicable",
            "type": [
                "string",
                "null"
            ],
            "description": "How the linking entry relates to the external entry: null for a general relation, and \"origin\" when the linking entry was obtained from the external entry."
        }
    }
}
```