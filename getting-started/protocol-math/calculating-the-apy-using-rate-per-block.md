# Calculating the APY Using Rate Per Block

The Annual Percentage Yield \(APY\) for supplying or borrowing in each market can be calculated using the value of `supplyRatePerBlock` \(for supply APY\) or `borrowRatePerBlock` \(for borrow APY\) in this formula:

```text
Rate = sToken.supplyRatePerBlock(); // Integer
Rate = 37893566
ETH Mantissa = 1 * 10 ^ 18 (ETH has 18 decimal places)
Blocks Per Day = 4 * 60 * 24 (based on 4 blocks occurring every minute)
Days Per Year = 365

APY = ((((Rate / ETH Mantissa * Blocks Per Day + 1) ^ Days Per Year - 1)) - 1) * 100
```

Here is an example of calculating the supply and borrow APY with Web3.js JavaScript:

```javascript
const ethMantissa = 1e18;
const blocksPerDay = 4 * 60 * 24;
const daysPerYear = 365;

const sToken = new web3.eth.Contract(sEthAbi, sEthAddress);
const supplyRatePerBlock = await sToken.methods.supplyRatePerBlock().call();
const borrowRatePerBlock = await sToken.methods.borrowRatePerBlock().call();
const supplyApy = (((Math.pow((supplyRatePerBlock / ethMantissa * blocksPerDay) + 1, daysPerYear))) - 1) * 100;
const borrowApy = (((Math.pow((borrowRatePerBlock / ethMantissa * blocksPerDay) + 1, daysPerYear))) - 1) * 100;
console.log(`Supply APY for ETH ${supplyApy} %`);
console.log(`Borrow APY for ETH ${borrowApy} %`);
```

