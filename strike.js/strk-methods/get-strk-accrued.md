# Get Strk Accrued

Get the amount of STRK tokens accrued but not yet claimed by an address.

* `_address` \(string\) The address in which to find the STRK accrued.
* `[_provider]` \(Provider \| string\) An Ethers.js provider or valid network name string.
* `RETURN` \(string\) Returns a string of the numeric accruement of STRK. The value is scaled up by 18 decimal places.

```text
(async function () {
  const acc = await Strike.strike.getStrikeAccrued('0x4Ddc2D193948926D02f9B1fE9e1daa0718270ED5');
  console.log('Accrued', acc);
})().catch(console.error);
```



