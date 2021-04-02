# sToken

Makes a request to the STokenService API. The sToken API retrieves information about sToken contract interaction. For more details, see the Strike API documentation.

* `options` \(object\) A JavaScript object of API request parameters.
* `RETURN` \(object\) Returns the HTTP response body or error.

```text
(async function() {
  const sEthData = await Strike.api.sToken({
    "addresses": Strike.util.getAddress(Strike.sETH)
  });

  console.log('sEthData', sEthData); // JavaScript Object
})().catch(console.error);
```

