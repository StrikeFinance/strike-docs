# Interpreting Exchange Rates

The sToken [Exchange Rate](../../stokens/exchange-rate.md) is scaled by the difference in decimals between the sToken and the underlying asset.

```javascript
const oneSTokenInUnderlying = exchangeRateCurrent / (1 * 10 ^ (18 + underlyingDecimals - sTokenDecimals))
```

Here is an example of finding the value of 1 cBAT in BAT with Web3.js JavaScript.

```javascript
const sTokenDecimals = 8; // all sTokens have 8 decimal places
const underlying = new web3.eth.Contract(erc20Abi, batAddress);
const sToken = new web3.eth.Contract(sTokenAbi, sUsdcAddress);
const underlyingDecimals = await underlying.methods.decimals().call();
const exchangeRateCurrent = await sToken.methods.exchangeRateCurrent().call();
const mantissa = 18 + parseInt(underlyingDecimals) - sTokenDecimals;
const oneSTokenInUnderlying = exchangeRateCurrent / Math.pow(10, mantissa);
console.log('1 sUSDC can be redeemed for', oneSTokenInUnderlying, 'USDC');
```

There is no underlying contract for ETH, so to do this with sETH, set `underlyingDecimals` to 18.

To find the number of underlying tokens that can be redeemed for sTokens, multiply the number of sTokens by the above value `oneSTokenInUnderlying`.

```javascript
const underlyingTokens = sTokenAmount * oneSTokenInUnderlying
```

