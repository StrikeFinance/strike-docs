# Repay Borrow

Repays a borrowed Ethereum asset for the user or on behalf of another Ethereum address.

* `asset` \(string\) A string of the asset that was borrowed \(must be a supported underlying asset\).
* `amount` \(number \| string \| BigNumber\) A string, number, or BigNumber object of the amount of an asset to borrow. Use the `mantissa` boolean in the `options` parameter to indicate if this value is scaled up \(so there are no decimals\) or in its natural scale.
* `[borrower]` \(string \| null\) The Ethereum address of the borrower to repay an open borrow for. Set this to `null` if the user is repaying their own borrow.
* `noApprove` \(boolean\) Explicitly prevent this method from attempting an ERC-20 `approve` transaction prior to sending the subsequent repayment transaction.
* `[options]` \(CallOptions\) Call options and Ethers.js overrides for the transaction. A passed `gasLimit` will be used in both the `approve` \(if not supressed\) and `repayBorrow` or `repayBorrowBehalf` transactions.
* `RETURN` \(object\) Returns an Ethers.js transaction object of the repayBorrow or repayBorrowBehalf transaction.

```text
const strike = new Strike(window.ethereum);

(async function() {

  console.log('Repaying Usdc borrow...');
  const address = null; // set this to any address to repayBorrowBehalf
  const trx = await strike.repayBorrow(Strike.USDC, 32, address);

  console.log('Ethers.js transaction object', trx);

})().catch(console.error);
```

