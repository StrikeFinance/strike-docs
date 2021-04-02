# Underlying Balance

The user's underlying balance, representing their assets in the protocol, is equal to the user's sToken balance multiplied by the [Exchange Rate](exchange-rate.md).

**SErc20 / SEther**

```text
function balanceOfUnderlying(address account) returns (uint)
```

* `account`: The account to get the underlying balance of.
* `RETURN`: The amount of underlying currently owned by the account.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint tokens = sToken.balanceOfUnderlying(msg.caller);
```

**Web3 1.0**

```text
const sToken = SEther.at(0x3FDB...);
const tokens = await sToken.methods.balanceOfUnderlying(account).call();
```

