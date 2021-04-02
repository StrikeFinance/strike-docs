# Redeem

The redeem function converts a specified quantity of sTokens into the underlying asset, and returns them to the user. The amount of underlying tokens received is equal to the quantity of sTokens redeemed, multiplied by the current [Exchange Rate](exchange-rate.md). The amount redeemed must be less than the user's [Account Liquidity](../comptroller/get-account-liquidity.md) and the market's available liquidity.

**SErc20 / SEther**

```text
function redeem(uint redeemTokens) returns (uint)
```

* `msg.sender`: The account to which redeemed funds shall be transferred.
* `redeemTokens`: The number of sTokens to be redeemed.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

**Solidity**

```text
SEther sToken = SEther(0x3FDB...);
require(sToken.redeem(7) == 0, "something went wrong");
```

**Web3 1.0**

```javascript
const sToken = SErc20.at(0x3FDA...);
sToken.methods.redeem(1).send({from: ...});
```

