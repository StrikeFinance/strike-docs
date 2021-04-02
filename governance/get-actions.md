# Get Actions

Gets the actions of a selected proposal. Pass a proposal ID and get the targets, values, signatures and calldatas of that proposal.

**Governor Alpha**

```text
function getActions(uint proposalId) returns (uint proposalId) public view returns (address[] memory targets, uint[] memory values, string[] memory signatures, bytes[] memory calldatas)
```

* `proposalId`: ID of a proposal in which to get its actions.
* `RETURN`: Reverts if the proposal ID is invalid. If successful, the following 4 references are returned. 1. Array of addresses of contracts the proposal calls. 2. Array of unsigned integers the proposal uses as values. 3. Array of strings of the proposal’s signatures. 4. Array of calldata bytes of the proposal.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
uint proposalId = 123;
(address[] memory targets, uint[] memory values, string[] memory signatures, bytes[] memory calldatas) = gov.getActions(proposalId);
```

**Web3 1.2.6**

```javascript
const {0: targets, 1: values, 2: signatures, 3: calldatas} = gov.methods.getActions(proposalId).call();
```

