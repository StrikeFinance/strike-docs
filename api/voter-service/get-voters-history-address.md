# GET: /voters/history/:address

#### VoterHistoryRequest

The request to the Voter History API can retrieve the vote history of the address.

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
| uint32 | `offset` | Limit of pagination |
| int32 | `limit` | Limit of pagination |
| uint32 | `total` | Total count of data |
| array | `result` | Array of `Voters` |

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

