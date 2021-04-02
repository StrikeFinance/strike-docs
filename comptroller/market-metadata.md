# Market Metadata

The Comptroller contract has an array called `allMarkets` that contains the addresses of each sToken contract. Each address in the `allMarkets` array can be used to fetch a metadata struct in the Comptroller’s markets constant. See the [Comptroller Storage contract](https://github.com/strike-finance/strike-protocol/blob/master/contracts/ComptrollerStorage.sol) for the Market struct definition.

**Comptroller**

```text
SToken[] public allMarkets;
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
SToken sTokens[] = troll.allMarkets();
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);
const sTokens = await comptroller.methods.allMarkets().call();
const sToken = sTokens[0]; // address of a sToken
```

