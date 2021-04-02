# Propose

Create a Proposal to change the protocol. E.g., A proposal can set a sToken's interest rate model or risk parameters on the Comptroller.

Proposals will be voted on by delegated voters. If there is sufficient support before the voting period ends, the proposal shall be automatically enacted. Enacted proposals are queued and executed in the Strike Timelock contract.

The sender must hold more STRK than the current proposal threshold \(`proposalThreshold()`\) as of the immediately previous block. If the threshold is 100,000 STRK, the sender must have been delegated more than 1% of all STRK in order to create a proposal. The proposal can have up to 10 actions \(based on `proposalMaxOperations()`\).

The proposer cannot create another proposal if they currently have a pending or active proposal. It is not possible to queue two identical actions in the same block \(due to a restriction in the Timelock\), therefore actions in a single proposal must be unique, and unique proposals that share an identical action must be queued in different blocks.

**Governor Alpha**

```text
function propose(address[] memory targets, uint[] memory values, string[] memory signatures, bytes[] memory calldatas, string memory description) returns (uint)
```

* `targets`: The ordered list of target addresses for calls to be made during proposal execution. This array must be the same length as all other array parameters in this function.
* `values`: The ordered list of values \(i.e. msg.value\) to be passed to the calls made during proposal execution. This array must be the same length as all other array parameters in this function.
* `signatures`: The ordered list of function signatures to be passed during execution. This array must be the same length as all other array parameters in this function.
* `calldatas`: The ordered list of data to be passed to each individual function call during proposal execution. This array must be the same length as all other array parameters in this function.
* `description`: A human readable description of the proposal and the changes it will enact.
* `RETURN`: The ID of the newly created proposal.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint proposalId = gov.propose(targets, values, signatures, calldatas, description);
```

**Web3 1.2.6**

```javascript
const tx = gov.methods.propose(targets, values, signatures, calldatas, description).send({ from: sender });
```

