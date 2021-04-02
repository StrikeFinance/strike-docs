# Close Factor

The percent, ranging from 0% to 100%, of a liquidatable account's borrow that can be repaid in a single liquidate transaction. If a user has multiple borrowed assets, the closeFactor applies to any single borrowed asset, not the aggregated value of a user’s outstanding borrowing.

**Comptroller**

```text
function closeFactorMantissa() view returns (uint)
```

* `RETURN`: The closeFactor, scaled by 1e18, is multiplied by an outstanding borrow balance to determine how much could be closed.

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
uint closeFactor = troll.closeFactorMantissa();
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const closeFactor = await troll.methods.closeFactoreMantissa().call();
```

