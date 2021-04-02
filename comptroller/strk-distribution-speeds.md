# STRK Distribution Speeds

## STRK Speed

The "STRK speed" unique to each market is an unsigned integer that specifies the amount of STRK that is distributed, per block, to suppliers and borrowers in each market. This number can be changed for individual markets by calling the `_setStrikeSpeed` method through a successful Strike Governance proposal.

The following is the formula for calculating the rate that STRK is distributed to each supported market.

```text
utility = sTokenTotalBorrows * assetPrice

utilityFraction = utility / sumOfAllStrikedMarketUtilities

marketStrikeSpeed = strikeRate * utilityFraction
```

## STRK Distributed Per Block \(All Markets\)

The Comptroller contract’s `strikeRate` is an unsigned integer that indicates the rate at which the protocol distributes STRK to markets’ suppliers or borrowers, every Ethereum block. The value is the amount of STRK \(in wei\), per block, allocated for the markets. Note that not every market has STRK distributed to its participants \(see Market Metadata\).

The strikeRate indicates how much STRK goes to the suppliers or borrowers, so doubling this number shows how much STRK goes to all suppliers and borrowers combined. The code examples implement reading the amount of STRK distributed, per Ethereum block, to all markets.

**Comptroller**

```text
uint public strikeRate;
```

**Solidity**

```text
Comptroller troll = Comptroller(0xABCD...);

// STRK issued per block to suppliers OR borrowers * (1 * 10 ^ 18)
uint strikeRate = troll.strikeRate();

// Approximate STRK issued per day to suppliers OR borrowers * (1 * 10 ^ 18)
uint strikeRatePerDay = strikeRate * 4 * 60 * 24;

// Approximate STRK issued per day to suppliers AND borrowers * (1 * 10 ^ 18)
uint strikeRatePerDayTotal = strikeRatePerDay * 2;
```

**Web3 1.2.6**

```javascript
const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);

let strikeRate = await comptroller.methods.strikeRate().call();
strikeRate = strikeRate / 1e18;

// STRK issued to suppliers OR borrowers
const strikeRatePerDay = strikeRate * 4 * 60 * 24;

// STRK issued to suppliers AND borrowers
const strikeRatePerDayTotal = strikeRatePerDay * 2;
```

## STRK Distributed Per Block \(Single Market\)

The Comptroller contract has a mapping called `strikeSpeeds`. It maps sToken addresses to an integer of each market’s STRK distribution per Ethereum block. The integer indicates the rate at which the protocol distributes STRK to markets’ suppliers or borrowers. The value is the amount of STRK \(in wei\), per block, allocated for the market. Note that not every market has STRK distributed to its participants \(see Market Metadata\).

The speed indicates how much STRK goes to the suppliers or the borrowers, so doubling this number shows how much STRK goes to market suppliers and borrowers combined. The code examples implement reading the amount of STRK distributed, per Ethereum block, to a single market.

**Comptroller**

```text
mapping(address => uint) public strikeSpeeds;
```

**Solidity**

```text
Comptroller troll = Comptroller(0x123...);
address sToken = 0xabc...;

// STRK issued per block to suppliers OR borrowers * (1 * 10 ^ 18)
uint strikeSpeed = troll.strikeSpeeds(sToken);

// Approximate STRK issued per day to suppliers OR borrowers * (1 * 10 ^ 18)
uint strikeSpeedPerDay = strikeSpeed * 4 * 60 * 24;

// Approximate STRK issued per day to suppliers AND borrowers * (1 * 10 ^ 18)
uint strikeSpeedPerDayTotal = strikeSpeedPerDay * 2;
```

**Web3 1.2.6**

```javascript
const sTokenAddress = '0xabc...';

const comptroller = new web3.eth.Contract(comptrollerAbi, comptrollerAddress);

let strikeSpeed = await comptroller.methods.strikeSpeeds(sTokenAddress).call();
strikeSpeed = strikeSpeed / 1e18;

// STRK issued to suppliers OR borrowers
const strikeSpeedPerDay = strikeSpeed * 4 * 60 * 24;

// STRK issued to suppliers AND borrowers
const strikeSpeedPerDayTotal = strikeSpeedPerDay * 2;
```

