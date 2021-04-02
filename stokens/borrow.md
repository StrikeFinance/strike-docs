# Borrow

The borrow function transfers an asset from the protocol to the user, and creates a borrow balance which begins accumulating interest based on the [Borrow Rate](borrow-rate.md) for the asset. The amount borrowed must be less than the user's [Account Liquidity](../comptroller/get-account-liquidity.md) and the market's available liquidity.

To borrow Ether, the borrower must be 'payable' \(solidity\).

**SErc20 / SEther**

```text
function borrow(uint borrowAmount) returns (uint)
```

* `msg.sender`: The account to which borrowed funds shall be transferred.
* `borrowAmount` : The amount of the underlying asset to be borrowed.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

**Solidity**

```text
SErc20 sToken = SErc20(0x3FDA...);
require(sToken.borrow(100) == 0, "got collateral?");
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
await sToken.methods.borrow(50).send({from: 0xMyAccount});
```

