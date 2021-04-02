# Cast Vote By Signature

Cast a vote on a proposal. The account's voting weight is determined by the number of votes the account had delegated at the time that proposal state became active. This method has the same purpose as Cast Vote but it instead enables offline signatures to participate in Strike governance voting. For more details on how to create an offline signature, review [EIP-712](https://eips.ethereum.org/EIPS/eip-712).

**Governor Alpha**

```text
function castVoteBySig(uint proposalId, bool support, uint8 v, bytes32 r, bytes32 s)
```

* `proposalId`: ID of a proposal in which to cast a vote.
* `support`: A boolean of true for 'yes' or false for 'no' on the proposal vote.
* `v`: The recovery byte of the signature.
* `r`: Half of the ECDSA signature pair.
* `s`: Half of the ECDSA signature pair.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
GovernorAlpha gov = GovernorAlpha(0x123...); // contract address
gov.castVoteBySig(proposalId, true, v, r, s);
```

**Web3 1.2.6**

```javascript
const tx = await gov.methods.castVoteBySig(proposalId, false, v, r, s).send({});
```

