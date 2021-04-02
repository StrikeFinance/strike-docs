# Get Balance

Fetches the current Ether balance of a provided Ethereum address.

* `address` \(string\) The Ethereum address in which to get the ETH balance.
* `[provider]` \(Provider \| string\) Optional Ethereum network provider. Defaults to Ethers.js fallback mainnet provider.
* `RETURN` \(BigNumber\) Returns a BigNumber hexadecimal value of the ETH balance of the address.

```text
(async function () {

  balance = await Strike.eth.getBalance(myAddress, provider);
  console.log('My ETH Balance', +balance);

})().catch(console.error);
```



