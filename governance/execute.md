# Execute

After the Timelock delay period, any account may invoke the execute method to apply the changes from the proposal to the target contracts. This will invoke each of the actions described in the proposal.

This function is payable so the Timelock contract can invoke payable functions that were selected in the proposal. E.g., A proposal can add reserves to a market like sETH, set a sToken's interest rate model, or set risk parameters on the Comptroller.

**Governor Alpha**

```text
function execute(uint proposalId) payable returns (uint)
```

* `proposalId`: ID of a succeeded proposal to execute.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
gov.execute(proposalId).value(999).gas(999)();
```

**Web3 1.2.6**

```javascript
const tx = gov.methods.execute(proposalId).send({ from: sender, value: 1 });
```

