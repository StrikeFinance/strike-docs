# Cast Vote By Sig

Submit a vote on a Strike Governance proposal using an EIP-712 signature.

* `proposalId` \(string\) The ID of the proposal to vote on. This is an auto-incrementing integer in the Governor Alpha contract.
* `support` \(boolean\) A boolean of true for 'yes' or false for 'no' on the proposal vote.
* `signature` \(object\) An object that contains the v, r, and, s values of an EIP-712 signature.
* `[options]` \(CallOptions\) Options to set for a transaction and Ethers.js method overrides.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the vote transaction.

```text
const strike = new Strike(window.ethereum);

(async function() {
  const castVoteTx = await strike.castVoteBySig(
    12,
    true,
    {
      v: '0x1b',
      r: '0x130dbcd2faca07424c033b4479687cc1deeb65f08509e3ab397988cc4c6f2e78',
      s: '0x1debcb8250262f23906b1177161f0c7c9aa3641e6bff5b6f5c88a6bb78d5d8cd'
    }
  );
  console.log('Ethers.js transaction object', castVoteTx);
})().catch(console.error);
```

