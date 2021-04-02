# Voting Delay

The number of Ethereum blocks to wait before voting on a proposal may begin. This value is added to the current block number when a proposal is created.

**Governor Alpha**

```text
function votingDelay() returns (uint)
```

* `RETURN`: Number of blocks to wait before voting on a proposal may begin.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint blocks = gov.votingDelay();
```

**Web3 1.2.6**

```javascript
const blocks = await gov.methods.votingDelay().call();
```

