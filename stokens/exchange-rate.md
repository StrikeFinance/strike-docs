# Exchange Rate

Each sToken is convertible into an ever increasing quantity of the underlying asset, as interest accrues in the market. The exchange rate between a sToken and the underlying asset is equal to:

```text
exchangeRate = (getCash() + totalBorrows() - totalReserves()) / totalSupply()
```

**SErc20 / SEther**

```text
function exchangeRateCurrent() returns (uint)
```

* `RETURN`: The current exchange rate as an unsigned integer, scaled by 1e18.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint exchangeRateMantissa = sToken.exchangeRateCurrent();
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const exchangeRate = (await sToken.methods.exchangeRateCurrent().call()) / 1e18;
```

Tip: note the use of call vs. send to invoke the function from off-chain without incurring gas costs.

