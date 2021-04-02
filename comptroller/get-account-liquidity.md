# Get Account Liquidity

Account Liquidity represents the USD value borrowable by a user, before it reaches liquidation. Users with a shortfall \(negative liquidity\) are subject to liquidation, and can’t withdraw or borrow assets until Account Liquidity is positive again.

For each market the user has [entered](enter-markets.md) into, their supplied balance is multiplied by the market’s [collateral factor](collateral-factor.md), and summed; borrow balances are then subtracted, to equal Account Liquidity. Borrowing an asset reduces Account Liquidity for each USD borrowed; withdrawing an asset reduces Account Liquidity by the asset’s collateral factor times each USD withdrawn.

Because the Strike Protocol exclusively uses unsigned integers, Account Liquidity returns either a surplus or shortfall.

**Comptroller**

```text
function getAccountLiquidity(address account) view returns (uint, uint, uint)
```

* `account`: The account whose liquidity shall be calculated.
* `RETURN`: Tuple of values \(error, liquidity, shortfall\). The error shall be 0 on success, otherwise an [error code](error-codes.md). A non-zero liquidity value indicates the account has available [account liquidity](get-account-liquidity.md). A non-zero shortfall value indicates the account is currently below his/her collateral requirement and is subject to liquidation. At most one of liquidity or shortfall shall be non-zero.

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
(uint error, uint liquidity, uint shortfall) = troll.getAccountLiquidity(msg.caller);
require(error == 0, "join the Discord");
require(shortfall == 0, "account underwater");
require(liquidity > 0, "account has excess collateral");
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const result = await troll.methods.getAccountLiquidity(0xBorrower).call();
const {0: error, 1: liquidity, 2: shortfall} = result;
```

