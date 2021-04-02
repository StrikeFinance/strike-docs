# Get ABI

Gets a contract ABI as a JavaScript array. This method supports contracts used by the Strike Protocol.

* `contract` \(string\) The name of the contract.
* `RETURN` \(Array\) Returns the ABI of the contract as a JavaScript array.

```text
console.log('sETH ABI: ', Strike.util.getAbi(Strike.sETH));
```



