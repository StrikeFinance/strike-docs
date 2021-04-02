# Claim Strk

Create a transaction to claim accrued STRK tokens for the user.

* `[options]` \(CallOptions\) Options to set for a transaction and Ethers.js method overrides.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the vote transaction.

```text
const strike = new Strike(window.ethereum);

(async function() {

  console.log('Claiming STRK...');
  const trx = await compound.claimStrike();
  console.log('Ethers.js transaction object', trx);

})().catch(console.error);
```

