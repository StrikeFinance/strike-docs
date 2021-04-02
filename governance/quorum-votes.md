# Quorum Votes

The required minimum number of votes in support of a proposal for it to succeed.

**Governor Alpha**

```text
function quorumVotes() public pure returns (uint)
```

* `RETURN`: The minimum number of votes required for a proposal to succeed.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint quorum = gov.quorumVotes();
```

**Web3 1.2.6**

```javascript
const quorum = await gov.methods.quorumVotes().call();
```

