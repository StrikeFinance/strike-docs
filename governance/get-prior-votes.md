# Get Prior Votes

Gets the prior number of votes for an account at a specific block number. The block number passed must be a finalized block or the function will revert.

**STRK**

```text
function getPriorVotes(address account, uint blockNumber) returns (uint96)
```

* `account`: Address of the account in which to retrieve the prior number of votes.
* `blockNumber`: The block number at which to retrieve the prior number of votes.
* `RETURN`: The number of prior votes.

**Solidity**

```text
Strk strk = Strk(0x123...); // contract address
uint priorVotes = strk.getPriorVotes(account, blockNumber);
```

**Web3 1.2.6**

```javascript
const priorVotes = await strk.methods.getPriorVotes(account, blockNumber).call();
```

