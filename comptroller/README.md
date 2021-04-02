# Comptroller

The Comptroller is the risk management layer of the Strike protocol; it determines how much collateral a user is required to maintain, and whether \(and by how much\) a user can be liquidated. Each time a user interacts with a sToken, the Comptroller is asked to approve or deny the transaction.

The Comptroller maps user balances to prices \(via the Price Oracle\) to risk weights \(called [Collateral Factors](collateral-factor.md)\) to make its determinations. Users explicitly list which assets they would like included in their risk scoring, by calling [Enter Markets](enter-markets.md) and [Exit Market](exit-market.md).

## Architecture

The Comptroller is implemented as an upgradeable proxy. The Unitroller proxies all logic to the Comptroller implementation, but storage values are set on the Unitroller. To call Comptroller functions, use the Comptroller ABI on the Unitroller address.

