# Borrow Balance

A user who borrows assets from the protocol is subject to accumulated interest based on the current [borrow rate](borrow-rate.md). Interest is accumulated every block and integrations may use this function to obtain the current value of a user's borrow balance with interest.

**SErc20 / SEther**

```text
function borrowBalanceCurrent(address account) returns (uint)
```

* `account`: The account which borrowed the assets.
* `RETURN`: The user's current borrow balance \(with interest\) in units of the underlying asset.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint borrows = sToken.borrowBalanceCurrent(msg.caller);
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const borrows = await sToken.methods.borrowBalanceCurrent(account).call();
```

