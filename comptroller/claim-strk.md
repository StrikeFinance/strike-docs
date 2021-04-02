# Claim STRK

Every Strike user accrues STRK for each block they are supplying to or borrowing from the protocol. Users may call the Comptroller's `claimStrike` method at any time to transfer STRK accrued to their address.

**Comptroller**

```text
// Claim all the STRK accrued by holder in all markets
function claimStrike(address holder) public

// Claim all the STRK accrued by holder in specific markets
function claimStrike(address holder, SToken[] memory sTokens) public

// Claim all the STRK accrued by specific holders in specific markets for their supplies and/or borrows
function claimStrike(address[] memory holders, SToken[] memory sTokens, bool borrowers, bool suppliers) public
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);
troll.claimStrike(0x1234...);
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);
await comptroller.methods.claimStrike("0x1234...").send({ from: sender });
```

