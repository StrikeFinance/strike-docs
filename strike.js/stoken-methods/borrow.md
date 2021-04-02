# Borrow

Borrows an Ethereum asset from the Strike Protocol for the user. The user's address must first have supplied collateral and entered a corresponding market.

* `asset` \(string\) A string of the asset to borrow \(must be a supported underlying asset\).
* `amount` \(number \| string \| BigNumber\) A string, number, or BigNumber object of the amount of an asset to borrow. Use the `mantissa` boolean in the `options` parameter to indicate if this value is scaled up \(so there are no decimals\) or in its natural scale.
* `[options]` \(CallOptions\) Call options and Ethers.js overrides for the transaction.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the borrow transaction.

```text
const strike = new Strike(window.ethereum);

(async function() {

  const usdtScaledUp = '32000000000000000000';
  const trxOptions = { mantissa: true };

  console.log('Borrowing 32 Usdt...');
  const trx = await strike.borrow(Strike.USDT, usdtScaledUp, trxOptions);

  console.log('Ethers.js transaction object', trx);

})().catch(console.error);
```

