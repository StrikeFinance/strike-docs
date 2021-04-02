# Reserve Factor

The reserve factor defines the portion of borrower interest that is converted into [reserves](total-reserves.md).

**SErc20 / SEther**

```text
function reserveFactorMantissa() returns (uint)
```

* `RETURN`: The current reserve factor as an unsigned integer, scaled by 1e18.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint reserveFactorMantissa = sToken.reserveFactorMantissa();
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const reserveFactor = (await sToken.methods.reserveFactorMantissa().call()) / 1e18;
```

