# Calculating Accrued Interest

Interest rates for each market update on any block in which the ratio of borrowed assets to supplied assets in the market has changed. The amount interest rates are changed depends on the interest rate model smart contract implemented for the market, and the amount of change in the ratio of borrowed assets to supplied assets in the market.

See the interest rate data visualization notebook on [Observable](https://observablehq.com/@jflatow/strike-interest-rates) to visualize which interest rate model is currently applied to each market.

Historical interest rates can be retrieved from the [MarketHistoryService API](../../api/markethistoryservice/).

Interest accrues to all suppliers and borrowers in a market when any Ethereum address interacts with the market’s sToken contract, calling one of these functions: mint, redeem, borrow, or repay. Successful execution of one of these functions triggers the accrueInterest method, which causes interest to be added to the underlying balance of every supplier and borrower in the market. Interest accrues for the current block, as well as each prior block in which the accrueInterest method was not triggered \(no user interacted with the sToken contract\). Interest strikes only during blocks in which the sToken contract has one of the aforementioned methods invoked.

Here is an example of supply interest accrual:

Alice supplies 1 ETH to the Strike protocol. At the time of supply, the `supplyRatePerBlock` is 37893605 Wei, or 0.000000000037893605 ETH per block. No one interacts with the sEther contract for 3 Ethereum blocks. On the subsequent 4th block, Bob borrows some ETH. Alice’s underlying balance is now 1.000000000151574420 ETH \(which is 37893605 Wei times 4 blocks, plus the original 1 ETH\). Alice’s underlying ETH balance in subsequent blocks will have interest accrued based on the new value of 1.000000000151574420 ETH instead of the initial 1 ETH. Note that the `supplyRatePerBlock` value may change at any time.

