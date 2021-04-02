# Cancel

Cancel a proposal that has not yet been executed. The Guardian is the only one who may execute this unless the proposer does not maintain the delegates required to create a proposal. If the proposer does not have more delegates than the proposal threshold, anyone can cancel the proposal.

**Governor Alpha**

```text
function cancel(uint proposalId)
```

* `proposalId`: ID of a proposal to cancel. The proposal cannot have already been executed.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
gov.cancel(proposalId);
```

**Web3 1.2.6**

```javascript
const tx = gov.methods.cancel(proposalId).send({ from: sender });
```

