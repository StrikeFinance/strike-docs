# Market History

Makes a request to the MarketHistoryService API. The market history service retrieves information about a market. For more details, see the Strike API documentation.

* `options` \(object\) A JavaScript object of API request parameters.
* `RETURN` \(object\) Returns the HTTP response body or error.

```text
(async function() {
  const sUsdcMarketData = await Strike.api.marketHistory({
    "asset": Strike.util.getAddress(Strike.sUSDC),
    "min_block_timestamp": 1559339900,
    "max_block_timestamp": 1598320674,
    "num_buckets": 10,
  });

  console.log('sUsdcMarketData', sUsdcMarketData); // JavaScript Object
})().catch(console.error);
```



