# Supply Rate

At any point in time one may query the contract to get the current supply rate per block. The supply rate is derived from the [borrow rate](borrow-rate.md), [reserve factor](reserve-factor.md) and the amount of [total borrows](total-borrow.md).

**SErc20 / SEther**

```text
function supplyRatePerBlock() returns (uint)
```

* `RETURN`: The current supply rate as an unsigned integer, scaled by 1e18.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint supplyRateMantissa = sToken.supplyRatePerBlock();
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const supplyRate = (await sToken.methods.supplyRatePerBlock().call()) / 1e18;
```

