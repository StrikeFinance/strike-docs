# Shared Data Types

Custom data types that are shared between services.

**Pagination Summary**

Used for paginating results.

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `offset` | The current offset |
| uint32 | `limit` | The number of entries to show per page. |
| uint32 | `total` | The number of items matching the request across all pages. |

**Precise**

For non-negative numbers only.

| Type | Key | Description |
| :--- | :--- | :--- |
| string | `value` | The full UNSIGNED number in string form. max value is 2^257 - 1,aka 231584178474632390847141970017375815706539969331281128078915168015826259279871 |

