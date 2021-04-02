# Protocol Math

The Strike protocol contracts use a system of exponential math, [Exponential.sol](https://github.com/strike-finance/strike-protocol/blob/master/contracts/Exponential.sol), in order to represent fractional quantities with sufficient precision.

Most numbers are represented as a mantissa, an unsigned integer scaled by `1 * 10 ^ 18`, in order to perform basic math at a high level of precision.

{% page-ref page="stoken-and-underlying-decimals.md" %}

{% page-ref page="interpreting-exchange-rates.md" %}

{% page-ref page="calculating-accrued-interest.md" %}

{% page-ref page="calculating-the-apy-using-rate-per-block.md" %}

