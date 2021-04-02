# Exit Market

Exits the user's address from a Strike Protocol market.

* `market` \(string\) A string of the symbol of the market to exit.
* `[options]` \(CallOptions\) Call options and Ethers.js overrides for the transaction. A passed `gasLimit` will be used in both the `approve` \(if not supressed\) and `mint` transactions.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the exitMarket transaction.

```text
const strike = new Strike(window.ethereum);

(async function () {
  const trx = await strike.exitMarket(Strike.ETH);
  console.log('Ethers.js transaction object', trx);
})().catch(console.error);
```



