# Proposal Max Operations

The maximum number of actions that can be included in a proposal. Actions are functions calls that will be made when a proposal succeeds and executes.

**Governor Alpha**

```text
function proposalMaxOperations() returns (uint)
```

* `RETURN`: The maximum number of actions that can be included in a proposal.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint operations = gov.proposalMaxOperations();
```

**Web3 1.2.6**

```javascript
const operations = await gov.methods.proposalMaxOperations().call();
```

