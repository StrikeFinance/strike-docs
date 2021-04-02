# Total Borrow

Total Borrows is the amount of underlying currently loaned out by the market, and the amount upon which interest is accumulated to suppliers of the market.

**SErc20 / SEther**

```text
function totalBorrowsCurrent() returns (uint)
```

* `RETURN`: The total amount of borrowed underlying, with interest.

**Solidity**

```text
SErc20 sToken = SToken(0x3FDA...);
uint borrows = sToken.totalBorrowsCurrent();
```

**Web3 1.0**

```javascript
const sToken = SEther.at(0x3FDB...);
const borrows = (await sToken.methods.totalBorrowsCurrent().call());
```

