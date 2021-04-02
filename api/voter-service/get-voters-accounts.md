# GET: /voters/accounts

#### VoterAccountsRequest

The voter accounts API returns information about all accounts participating in the vote.

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `offset` | Offset of pagination. `Default: 0` |
| uint32 | `limit` | Limit of pagination. `Max: 100` |

**VoterAccountsResponse**

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| voterAccountsData | `data` | Voter Account data. |

**VoterAccountsData**

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `offset` | Limit of pagination |
| int32 | `limit` | Limit of pagination |
| uint32 | `total` | Total count of data |
| array | `result` | Array of `VoterAccounts` |

**VoterAccounts**

| Type | Key | Description |
| :--- | :--- | :--- |
| uuid | `id` | Voter account id |
| string | `address` | Voter address |
| float | `voteWeight` | Vote weight |
| uint32 | `proposalVoted` | Proposal count to vote |
| string | `votes` | Votes |
| datetime | `createdAt` | Created timestamp |
| datetime | `updatedAt` | Updated timestamp |



