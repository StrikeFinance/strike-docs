# Create Delegate Signature

Create a delegate signature for Strike Governance using EIP-712. The signature can be created without burning gas. Anyone can post it to the blockchain using the delegateBySig method, which does have gas costs.

* `delegatee` \(string\) The address to delegate the user's voting rights to.
* `[expiry]` \(number\) The time at which to expire the signature. A block timestamp as seconds since the unix epoch. Defaults to `10e9`.
* `RETURN` \(object\) Returns an object that contains the `v`, `r`, and `s` components of an Ethereum signature as hexadecimal strings.

```text
const strike = new Strike(window.ethereum);

(async () => {

  const delegateSignature = await strike.createDelegateSignature('0xa0df350d2637096571F7A701CBc1C5fdE30dF76A');
  console.log('delegateSignature', delegateSignature);

})().catch(console.error);
```

