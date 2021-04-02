# GET: /market\_history/graph

**MarketHistoryGraphRequest**

The market history graph API returns information about a market between two timestamps. The requestor can choose the asset and number of buckets to return within the range. For example:

```text
{
 "asset": "0xf5dce57282a584d2746faf1593d3121fcac444dc",
 "type": "1day",
 "offset": 0,
 "limit": 100
}
```

| Type | Key | Description |
| :--- | :--- | :--- |
| bytes | `asset` | The requested asset |
| string | `type` | Graph log interval. `Enum["1day", "1hr"]` |
| uint32 | `offset` | Offset of pagination. `Default: 0` |
| uint32 | `limit` | Limit of pagination. `Max: 365` |

**MarketHistoryGraphResponse**

The market history graph API response contains the rates for both suppliers and borrowers, as well as the sequence of total supply and borrows for the given market.

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| MarketHistoryGraphData | `data` | Market history graph data. |

**MarketHistoryGraphData**

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `limit` | Limit of pagination |
| uint32 | `total` | Total count of data |
| array | `result` | Array of `MarketHistoryGraph` |

**MarketHistoryGraph**

| Type | Key | Description |
| :--- | :--- | :--- |
| uuid | `id` | History id |
| string | `asset` | Asset address |
| uint32 | `blockNumber` | Block number of graph history |
| uint32 | `blockTimestamp` | Unix block timestamp |
| string | `borrowApy` | Borrow apy |
| string | `supplyApy` | Supply apy |
| string | `borrowStrikeApy` | Borrow strk apy |
| string | `supplyStrikeApy` | Supply strk apy |
| string | `exchangeRate` | Exchange rate |
| string | `priceUSD` | USD price of asset |
| string | `totalBorrow` | Total borrow amount |
| string | `totalSupply` | Total supply amount |
| datetime | `createdAt` | Created timestamp |
| datetime | `updatedAt` | Updated timestamp |

