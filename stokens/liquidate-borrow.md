# Liquidate Borrow

A user who has negative [account liquidity](https://github.com/StrikePrivate/strike-docs/tree/294e07fcebce7997c93709b5b9f8bbdb7e8271af/stokens/comptroller/get-account-liquidity.md) is subject to [liquidation](https://github.com/StrikePrivate/strike-docs/tree/294e07fcebce7997c93709b5b9f8bbdb7e8271af/stokens/stokens/liquidate-borrow/README.md) by other users of the protocol to return his/her account liquidity back to positive \(i.e. above the collateral requirement\). When a liquidation occurs, a liquidator may repay some or all of an outstanding borrow on behalf of a borrower and in return receive a discounted amount of collateral held by the borrower; this discount is defined as the liquidation incentive.

A liquidator may close up to a certain fixed percentage \(i.e. close factor\) of any individual outstanding borrow of the underwater account. Unlike in v1, liquidators must interact with each sToken contract in which they wish to repay a borrow and seize another asset as collateral. When collateral is seized, the liquidator is transferred sTokens, which they may redeem the same as if they had supplied the asset themselves. Users must approve each sToken contract before calling liquidate \(i.e. on the borrowed asset which they are repaying\), as they are transferring funds into the contract.

**SErc20**

```text
function liquidateBorrow(address borrower, uint amount, address collateral) returns (uint)
```

* `msg.sender`: The account which shall liquidate the borrower by repaying their debt and seizing their collateral.
* `borrower`: The account with negative [account liquidity](../comptroller/get-account-liquidity.md) that shall be liquidated.
* `repayAmount`: The amount of the borrowed asset to be repaid and converted into collateral, specified in units of the underlying borrowed asset.
* `sTokenCollateral`: The address of the sToken currently held as collateral by a borrower, that the liquidator shall seize.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

Before supplying an asset, users must first [approve](https://eips.ethereum.org/EIPS/eip-20#approve) the sToken to access their token balance.

**SEther**

```text
function liquidateBorrow(address borrower, address sTokenCollateral) payable
```

* `msg.value` _\[payable\]_: The amount of ether to be repaid and converted into collateral, in wei.
* `msg.sender`: The account which shall liquidate the borrower by repaying their debt and seizing their collateral.
* `borrower`: The account with negative [account liquidity](../comptroller/get-account-liquidity.md) that shall be liquidated.
* `sTokenCollateral`: The address of the sToken currently held as collateral by a borrower, that the liquidator shall seize.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
SEther sToken = SEther(0x3FDB...);
SErc20 sTokenCollateral = SErc20(0x3FDA...);
require(sToken.liquidateBorrow.value(100)(0xBorrower, sTokenCollateral) == 0, "borrower underwater??");
```

**Web3 1.0**

```javascript
const sToken = SErc20.at(0x3FDA...);
const sTokenCollateral = SEther.at(0x3FDB...);
await sToken.methods.liquidateBorrow(0xBorrower, 33, sTokenCollateral).send({from: 0xLiquidator});
```

