# Proposal Threshold

The minimum number of votes required for an account to create a proposal.

**Governor Alpha**

```text
function proposalThreshold() returns (uint)
```

* `RETURN`: The minimum number of votes required for an account to create a proposal.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint threshold = gov.proposalThreshold();
```

**Web3 1.2.6**

```javascript
const threshold = await gov.methods.proposalThreshold().call();
```

