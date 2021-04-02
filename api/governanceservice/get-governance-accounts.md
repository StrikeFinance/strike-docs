# GET: /governance/accounts

**GovernanceAccountRequest**

The request to the Governance Account API can specify a number of filters, such as which accounts to retrieve information about.

| Type | Key | Description |
| :--- | :--- | :--- |
| bytes | `addresses` | A list of accounts to filter on, e.g.:?addresses=0x... |
| string | `order_by` | Filter for accounts by. E.g. “votes” \| “balance” \| “proposals\_created” \(`reserved`\) |
| bool | `with_history` | Will populate a list of transaction history for the accounts when request is submittedwith\_history=true \(`reserved`\) |
| uint32 | `limit` | Number of accounts to include in the response, default is 100 |
| uint32 | `offset` | Pagination offset for accounts in the response, default is 0 |

**GovernanceAccountResponse**

The Governance Account API returns a list of accounts that match the given filters on the request

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| StrikeAccountData | `data` | The list of governance accounts matching the requested filter |

**StrikeAccountData**

| **Type** | Key | Description |
| :--- | :--- | :--- |
| uint32 | `offset` | Offset of pagination |
| uint32 | `limit` | Limit of pagination |
| uint32 | `total` | Total count of pagination |
| StrikeAccount | `result` | The list of governance accounts matching the requested filter |

**StrikeAccount**

| Type | Key | Description |
| :--- | :--- | :--- |
| uuid | `id` | Unique id of StrikeAccount |
| bytes | `address` | The address of the given STRK account |
| float | `voteWeight` | The percentage of voting weight of total STRK |
| uint32 | `proposalsVoted` | The number of proposals voted on in the Strike Governance System |
| string | `votes` | Voting power |
| datetime | `createdAt` | Created timestamp |
| datetime | `updatedAt` | Updated timestamp |

