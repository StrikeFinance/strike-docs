# Get Address

Gets the contract address of the named contract. This method supports contracts used by the Strike Protocol.

* `contract` \(string\) The name of the contract.
* `[network]` \(string\) Optional name of the Ethereum network. Main net and all the popular public test nets are supported.
* `RETURN` \(string\) Returns the address of the contract.

```text
console.log('sETH Address: ', Strike.util.getAddress(Strike.sETH));
```

