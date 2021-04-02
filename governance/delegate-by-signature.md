# Delegate By Signature

Delegate votes from the signatory to the delegatee. This method has the same purpose as Delegate but it instead enables offline signatures to participate in Strike governance vote delegation. For more details on how to create an offline signature, review [EIP-712](https://eips.ethereum.org/EIPS/eip-712).

**STRK**

```text
function delegateBySig(address delegatee, uint nonce, uint expiry, uint8 v, bytes32 r, bytes32 s)
```

* `delegatee`: The address in which the sender wishes to delegate their votes to.
* `nonce`: The contract state required to match the signature. This can be retrieved from the contract’s public nonces mapping.
* `expiry`: The time at which to expire the signature. A block timestamp as seconds since the unix epoch \(uint\).
* `v`: The recovery byte of the signature.
* `r`: Half of the ECDSA signature pair.
* `s`: Half of the ECDSA signature pair.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
Strk strk = Strk(0x123...); // contract address
strk.delegateBySig(delegateeAddress, nonce, expiry, v, r, s);
```

**Web3 1.2.6**

```javascript
const tx = await strk.methods.delegateBySig(delegateeAddress, nonce, expiry, v, r, s).send({});
```

