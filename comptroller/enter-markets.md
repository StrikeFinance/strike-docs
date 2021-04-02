# Enter Markets

Enter into a list of markets - it is not an error to enter the same market more than once. In order to supply collateral or borrow in a market, it must be entered first.

**Comptroller**

```text
function enterMarkets(address[] calldata sTokens) returns (uint[] memory)
```

* `msg.sender`: The account which shall enter the given markets.
* `sTokens`: The addresses of the sToken markets to enter.
* `RETURN`: For each market, returns an error code indicating whether or not it was entered. Each is 0 on success, otherwise an [Error code](error-codes.md).

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
SToken[] memory sTokens = new SToken[](2);
sTokens[0] = SErc20(0x3FDA...);
sTokens[1] = SEther(0x3FDB...);
uint[] memory errors = troll.enterMarkets(sTokens);
```

**Web3 1.0**

```javascript
const troll = Comptroller.at(0xABCD...);
const sTokens = [SErc20.at(0x3FDA...), SEther.at(0x3FDB...)];
const errors = await troll.methods.enterMarkets(sTokens).send({from: ...});
```

