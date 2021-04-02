# Get Cash

Cash is the amount of underlying balance owned by this sToken contract. One may query the total amount of cash currently available to this market.

**SErc20 / SEther**

```text
function getCash() returns (uint)
```

* `RETURN`: The quantity of underlying asset owned by the contract.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint cash = sToken.getCash();
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const cash = (await sToken.methods.getCash().call());
```

