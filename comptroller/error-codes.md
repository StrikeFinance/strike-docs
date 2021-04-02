# Error Codes

| Code | Name | Description |
| :--- | :--- | :--- |
| 0 | `NO_ERROR` | Not a failure. |
| 1 | `UNAUTHORIZED` | The sender is not authorized to perform this action. |
| 2 | `COMPTROLLER_MISMATCH` | Liquidation cannot be performed in markets with different comptrollers. |
| 3 | `INSUFFICIENT_SHORTFALL` | The account does not have sufficient shortfall to perform this action. |
| 4 | `INSUFFICIENT_LIQUIDITY` | The account does not have sufficient liquidity to perform this action. |
| 5 | `INVALID_CLOSE_FACTOR` | The close factor is not valid. |
| 6 | `INVALID_COLLATERAL_FACTOR` | The collateral factor is not valid. |
| 7 | `INVALID_LIQUIDATION_INCENTIVE` | The liquidation incentive is invalid. |
| 8 | `MARKET_NOT_ENTERED` | The market has not been entered by the account. |
| 9 | `MARKET_NOT_LISTED` | The market is not currently listed by the comptroller. |
| 10 | `MARKET_ALREADY_LISTED` | An admin tried to list the same market more than once. |
| 11 | `MATH_ERROR` | A math calculation error occurred. |
| 12 | `NONZERO_BORROW_BALANCE` | The action cannot be performed since the account carries a borrow balance. |
| 13 | `PRICE_ERROR` | The comptroller could not obtain a required price of an asset. |
| 14 | `REJECTION` | The comptroller rejects the action requested by the market. |
| 15 | `SNAPSHOT_ERROR` | The comptroller could not get the account borrows and exchange rate from the market. |
| 16 | `TOO_MANY_ASSETS` | Attempted to enter more markets than are currently supported. |
| 17 | `TOO_MUCH_REPAY` | Attempted to repay more than is allowed by the protocol. |

