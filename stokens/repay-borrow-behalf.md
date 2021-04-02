# Repay Borrow Behalf

The repay function transfers an asset into the protocol, reducing the target user's borrow balance.

**SErc20**

```text
function repayBorrowBehalf(address borrower, uint repayAmount) returns (uint)
```

* `msg.sender`: The account which shall repay the borrow.
* `borrower`: The account which borrowed the asset to be repaid.
* `repayAmount`: The amount of the underlying borrowed asset to be repaid. A value of -1 \(i.e. 2 ^ 256 - 1\) can be used to repay the full amount.
* `RETURN`: 0 on success, otherwise an [Error code](error-codes.md)

Before repaying an asset, users must first [approve](https://eips.ethereum.org/EIPS/eip-20#approve) the sToken to access their token balance.

**SEther**

```text
function repayBorrowBehalf(address borrower) payable
```

* `msg.value` _\[payable\]_: The amount of ether to be repaid, in wei.
* `msg.sender`: The account which shall repay the borrow.
* `borrower`: The account which borrowed the asset to be repaid.
* `RETURN`: No return, reverts on error.

**Solidity**

```text
SEther sToken = SEther(0x3FDB...);
require(sToken.repayBorrowBehalf.value(100)(0xBorrower) == 0, "transfer approved?");
```

**Web3 1.0**

```javascript
const sToken = SErc20.at(0x3FDA...);
await sToken.methods.repayBorrowBehalf(0xBorrower, 10000).send({from: 0xPayer});
```

