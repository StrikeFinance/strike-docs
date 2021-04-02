# Get Receipt

Gets a proposal ballot receipt of the indicated voter.

**Governor Alpha**

```text
function getReceipt(uint proposalId, address voter) returns (Receipt memory)
```

* `proposalId`: ID of the proposal in which to get a voter’s ballot receipt.
* `voter`: Address of the account of a proposal voter.
* `RETURN`: Reverts on error. If successful, returns a Receipt struct for the ballot of the voter address.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
Receipt ballot = gov.getReceipt(proposalId, voterAddress);
```

**Web3 1.2.6**

```javascript
const proposalId = 11;
const voterAddress = '0x123...';
const result = await gov.methods.getReceipt(proposalId, voterAddress).call();
const { hasVoted, support, votes } = result;
```

