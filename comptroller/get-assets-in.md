# Get Assets In

Get the list of markets an account is currently entered into. In order to supply collateral or borrow in a market, it must be entered first. Entered markets count towards [account liquidity](get-account-liquidity.md) calculations.

**Comptroller**

```text
function getAssetsIn(address account) view returns (address[] memory)
```

* `account`: The account whose list of entered markets shall be queried.
* `RETURN`: The address of each market which is currently entered into.

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
address[] memory markets = troll.getAssetsIn(0xMyAccount);
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const markets = await troll.methods.getAssetsIn(sTokens).call();
```

