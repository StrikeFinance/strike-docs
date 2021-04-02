# Get Strk Balance

Get the balance of STRK tokens held by an address.

* `_address` \(string\) The address in which to find the STRK balance.
* `[_provider]` \(Provider \| string\) An Ethers.js provider or valid network name string.
* `RETURN` \(string\) Returns a string of the numeric balance of STRK. The value is scaled up by 18 decimal places.

```text
(async function () {
  const bal = await Strike.strike.getStrikeBalance('0x2775b1c75658Be0F640272CCb8c72ac986009e38');
  console.log('Balance', bal);
})().catch(console.error);
```

