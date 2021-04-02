# GET: /voters/:proposalId

#### VoterProposalRequest

The request to the Voter Proposal API can specify a number of filters, such as which accounts to retrieve information about.

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `offset` | Offset of pagination. `Default: 0` |
| uint32 | `limit` | Limit of pagination. `Max: 100` |
| string | `filter` | Filter for support |

**VoterProposalResponse**

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| voterData | `data` | Voter data. |

**VoterData**

| Type | Key | Description |
| :--- | :--- | :--- |
| int32 | `limit` | Limit of pagination |
| uint32 | `total` | Total count of data |
| array | `result` | Array of `Voters` |
| string | sumVotes | The sum of all votes |

**Voters**

| Type | Key | Description |
| :--- | :--- | :--- |
| uuid | `id` | Voter id |
| string | `address` | Voter address |
| int8 | `hasVoted` | Vote status |
| int8 | `support` | Support status |
| int20 | `proposalId` | Vote proposal Index |
| datetime | `blockNumber` | Block Number |
| datetime | `blocktimestamp` | Block timestamp |
| datetime | `createdAt` | Created timestamp |
| datetime | `updatedAt` | Updated timestamp |

