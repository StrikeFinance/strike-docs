# Voting Period

The duration of voting on a proposal, in Ethereum blocks.

**Governor Alpha**

```text
function votingPeriod() returns (uint)
```

* `RETURN`: The duration of voting on a proposal, in Ethereum blocks.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint blocks = gov.votingPeriod();
```

**Web3 1.2.6**

```javascript
const blocks = await gov.methods.votingPeriod().call();
```

