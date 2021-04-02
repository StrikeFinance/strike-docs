# Supply

Supplies the user's Ethereum asset to the Strike Protocol.

* `asset` \(string\) A string of the asset to supply.
* `amount` \(number \| string \| BigNumber\) A string, number, or BigNumber object of the amount of an asset to supply. Use the `mantissa` boolean in the `options` parameter to indicate if this value is scaled up \(so there are no decimals\) or in its natural scale.
* `noApprove` \(boolean\) Explicitly prevent this method from attempting an ERC-20 `approve` transaction prior to sending the `mint` transaction.
* `[options]` \(CallOptions\) Call options and Ethers.js overrides for the transaction. A passed `gasLimit` will be used in both the `approve` \(if not supressed\) and `mint` transactions.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the supply transaction.

```text
const strike = new Strike(window.ethereum);

// Ethers.js overrides are an optional 3rd parameter for `supply`
// const trxOptions = { gasLimit: 250000, mantissa: false };

(async function() {

  console.log('Supplying ETH to the Strike Protocol...');
  const trx = await strike.supply(Strike.ETH, 1);
  console.log('Ethers.js transaction object', trx);

})().catch(console.error);
```



