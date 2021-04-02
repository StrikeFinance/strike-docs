# Liquidation Incentive

The additional collateral given to liquidators as an incentive to perform liquidation of underwater accounts. For example, if the liquidation incentive is 1.1, liquidators receive an extra 10% of the borrowers collateral for every unit they close.

**Comptroller**

```text
function liquidationIncentiveMantissa() view returns (uint)
```

* `RETURN`: The liquidationIncentive, scaled by 1e18, is multiplied by the closed borrow amount from the liquidator to determine how much collateral can be seized.

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
uint closeFactor = troll.liquidationIncentiveMantissa();
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const closeFactor = await troll.methods.liquidationIncentiveMantissa().call();
```

