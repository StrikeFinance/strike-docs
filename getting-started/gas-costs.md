# Gas Costs

The gas usage of the protocol functions may fluctuate by market and user. External calls, such as to underlying ERC-20 tokens, may use an arbitrary amount of gas. Any calculations that involve checking [account liquidity](../comptroller/get-account-liquidity.md), have gas costs that increase with the number of [entered markets](../comptroller/enter-markets.md). Thus, while it can be difficult to provide any guarantees about costs, we provide the table below for guidance:

| Function | Typical Gas Cost |
| :--- | :--- |
| Mint | &lt; 150K, sUSDC &lt; 300k |
| Redeem, Transfer | &lt; 250K if borrowing, otherwise &lt; 90K |
| Borrow | &lt; 300K |
| Repay Borrow | &lt; 90K |
| Liquidate Borrow | &lt; 400K |

