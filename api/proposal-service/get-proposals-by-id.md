---
description: Get proposal info by id.
---

# GET: /proposals/:id

**ProposalsResponse**‌

The API response contains the proposal data of the given proposal id.

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| Proposal | `data` | Proposal data. |

**Proposal**

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `id` | Unique id for looking up a proposal |
| string | `description` | A description of the actions the proposal will take if successful |
| bytes | `targets` | The address to send the calldata to |
| string | `values` | The value of ETH to send with the transaction |
| string | `signatures` | The function signature of the function to call at the target address |
| string | `calldatas` | The encoded argument data for the action |
| uint32 | `createdBlock` | Created block number |
| string | `createdTxHash` | Created transaction hash |
| uint32 | `createdTimestamp` | Created block timestamp |
| uint32 | `startBlock` | Started block number |
| string | `startTxHash` | Started transaction hash |
| uint32 | `startTimestamp` | Started block timestamp |
| uint32 | `cancelBlock` | Canceled block number |
| string | `cancelTxHash` | Canceled transaction hash |
| uint32 | `cancelTimestamp` | Canceled block timestamp |
| uint32 | `endBlock` | End block number |
| string | `endTxHash` | End transaction hash |
| uint32 | `endTimestamp` | End block timestamp |
| uint32 | `queuedBlock` | Queued block number |
| string | `queuedTxHash` | Queued transaction hash |
| uint32 | `queuedTimestamp` | Queued block timestamp |
| uint32 | `executedBlock` | Executed block number |
| string | `executedTxHash` | Executed transaction hash |
| uint32 | `executedTimestamp` | Executed block timestamp |
| bytes | `proposer` | Proposer address |
| uint32 | `eta` | eta |
| string | `forVotes` | The number of votes in support of the proposal |
| string | `againstVotes` | The number of votes in opposition to this proposal |
| bool | `canceled` | Set true if canceled |
| bool | executed | Set true if executed |
| string | `state` | State of `"Pending", "Active", "Canceled", "Defeated", "Succeeded", "Queued", "Expired", "Executed"` |
| uint32 | `voterCount` | Voter count |
| uint32 | `blockNumber` | Last calculated block number |



