# sToken and Underlying Decimals

Prices and exchange rates are scaled by the decimals unique to each asset; sTokens are ERC-20 tokens with 8 decimals, while their underlying tokens vary, and have a public member named _decimals_.

| sToken | sToken Decimals | Underlying | Underlying Decimals |
| :--- | :--- | :--- | :--- |
| sETH | 8 | ETH | 18 |
| sUSDC | 8 | USDC | 6 |
| sUSDT | 8 | USDT | 6 |
| sBUSD | 8 | BUSD | 18 |
| sLINK | 8 | LINK | 18 |
| sUNI | 8 | UNI | 18 |
| sCOMP | 8 | COMP | 18 |
| sWBTC | 8 | WBTC | 8 |
| sSTRK | 8 | STRK | 18 |

