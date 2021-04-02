# Account

Makes a request to the AccountService API. The Account API retrieves information for various accounts which have interacted with the protocol. For more details, see the Strike API documentation.

* `options` \(object\) A JavaScript object of API request parameters.
* `RETURN` \(object\) Returns the HTTP response body or error.

```text
(async function() {
  const account = await Strike.api.account({
    "addresses": "0xB61C5971d9c0472befceFfbE662555B78284c307",
    "network": "ropsten"
  });

  let usdtBorrowBalance = 0;
  if (Object.isExtensible(account) && account.accounts) {
    account.accounts.forEach((acc) => {
      acc.tokens.forEach((tok) => {
        if (tok.symbol === Strike.sUSDT) {
          usdtBorrowBalance = +tok.borrow_balance_underlying.value;
        }
      });
    });
  }

  console.log('usdtBorrowBalance', usdtBorrowBalance);
})().catch(console.error);
```

