# GET: /voters/accounts/:address

#### VoterAccountsRequest

The request to the Voter accounts API can retrieve information about the certain account.

| Type | Key | Description |
| :--- | :--- | :--- |
| string | `address` | Address to retrieve. `required` |

**VoterResponse**

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| voterData | `data` | Voter data. |

**VoterData**

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `delegateCount` | Delegate count of address |
| uint32 | `votes` | Current votes of address |
| uint32 | `balance` | SToken balance of address |
| array | `delegates` | Array of `Delegates` |
| array | `txs` | Array of `Transfer and vote transactions` |



