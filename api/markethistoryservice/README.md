# MarketHistoryService

The market history service retrieves historical information about a market. You can use this API to find out the values of interest rates at a certain point in time. Its especially useful for making charts and graphs of the time-series values.

```text
// Returns 10 buckets of market data
fetch("https://api.strike.org/api/market_history/graph?asset=0xf5dce57282a584d2746faf1593d3121fcac444dc&type=1day");
```

{% page-ref page="get-graph.md" %}



