# Get Price

Gets an asset's price from the Strike Protocol open price feed. The price of the asset can be returned in any other supported asset value, including all sTokens and underlyings.

* `asset` \(string\) A string of a supported asset in which to find the current price.
* `[inAsset]` \(string\) A string of a supported asset in which to express the `asset` parameter's price. This defaults to USD.
* `RETURN` \(string\) Returns a string of the numeric value of the asset.

```text
const strike = new Strike(window.ethereum);
let price;

(async function () {

  price = await strike.getPrice(Strike.WBTC);
  console.log('WBTC in USD', price); // 6 decimals, see Open Price Feed docs

  price = await strike.getPrice(Strike.ETH, Strike.USDC); // supports sTokens too
  console.log('ETH in USDC', price);

})().catch(console.error);
```

