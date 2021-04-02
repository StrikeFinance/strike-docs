# Cast Vote

Cast a vote on a proposal. The account's voting weight is determined by the number of votes the account had delegated to it at the time the proposal state became active.

**Governor Alpha**

```text
function castVote(uint proposalId, bool support)
```

* `proposalId`: ID of a proposal in which to cast a vote.
* `support`: A boolean of true for 'yes' or false for 'no' on the proposal vote.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
gov.castVote(proposalId, true);
```

**Web3 1.2.6**

```javascript
const tx = gov.methods.castVote(proposalId, false).send({ from: sender });
```

