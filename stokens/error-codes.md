# Error Codes

| Code | Name | Description |
| :--- | :--- | :--- |
| 0 | `NO_ERROR` | Not a failure. |
| 1 | `UNAUTHORIZED` | The sender is not authorized to perform this action. |
| 2 | `BAD_INPUT` | An invalid argument was supplied by the caller. |
| 3 | `COMPTROLLER_REJECTION` | The action would violate the comptroller policy. |
| 4 | `COMPTROLLER_CALCULATION_ERROR` | An internal calculation has failed in the comptroller. |
| 5 | `INTEREST_RATE_MODEL_ERROR` | The interest rate model returned an invalid value. |
| 6 | `INVALID_ACCOUNT_PAIR` | The specified combination of accounts is invalid. |
| 7 | `INVALID_CLOSE_AMOUNT_REQUESTED` | The amount to liquidate is invalid. |
| 8 | `INVALID_COLLATERAL_FACTOR` | The collateral factor is invalid. |
| 9 | `MATH_ERROR` | A math calculation error occurred. |
| 10 | `MARKET_NOT_FRESH` | Interest has not been properly accrued. |
| 11 | `MARKET_NOT_LISTED` | The market is not currently listed by its comptroller. |
| 12 | `TOKEN_INSUFFICIENT_ALLOWANCE` | ERC-20 contract must _allow_ Money Market contract to call transferFrom. The current allowance is either 0 or less than the requested supply, repayBorrow or liquidate amount. |
| 13 | `TOKEN_INSUFFICIENT_BALANCE` | Caller does not have sufficient balance in the ERC-20 contract to complete the desired action. |
| 14 | `TOKEN_INSUFFICIENT_CASH` | The market does not have a sufficient cash balance to complete the transaction. You may attempt this transaction again later. |
| 15 | `TOKEN_TRANSFER_IN_FAILED` | Failure in ERC-20 when transfering token into the market. |
| 16 | `TOKEN_TRANSFER_OUT_FAILED` | Failure in ERC-20 when transfering token out of the market. |

