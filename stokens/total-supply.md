# Total Supply

Total Supply is the number of tokens currently in circulation in this sToken market. It is part of the EIP-20 interface of the sToken contract.

**SErc20 / SEther**

```text
function totalSupply() returns (uint)
```

* `RETURN`: The total number of tokens in circulation for the market.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint tokens = sToken.totalSupply();
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const tokens = (await sToken.methods.totalSupply().call());
```

