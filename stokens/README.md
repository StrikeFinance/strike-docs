# STokens

Each asset supported by the Strike Protocol is integrated through a sToken contract, which is an [EIP-20](https://eips.ethereum.org/EIPS/eip-20) compliant representation of balances supplied to the protocol. By minting sTokens, users \(1\) earn interest through the sToken's exchange rate, which increases in value relative to the underlying asset, and \(2\) gain the ability to use sTokens as collateral.

sTokens are the primary means of interacting with the Strike Protocol; when a user mints, redeems, borrows, repays a borrow, liquidates a borrow, or transfers sTokens, she will do so using the sToken contract.

There are currently two types of sTokens: SErc20 and SEther. Though both types expose the EIP-20 interface, SErc20 wraps an underlying ERC-20 asset, while SEther simply wraps Ether itself. As such, the core functions which involve transferring an asset into the protocol have slightly different interfaces depending on the type, each of which is shown below.

## How do sTokens earn interest?

Each [market](https://strike.org/markets) has its own Supply interest rate \(APR\). Interest isn't distributed; instead, simply by holding sTokens, you'll earn interest.

sTokens accumulates interest through their exchange rate — over time, each sToken becomes convertible into an increasing amount of it's underlying asset, even while the number of sTokens in your wallet stays the same.

## Can you walk me through an example?

Let’s say you supply 1,000 USDC to the Strike protocol, when the exchange rate is 0.020070; you would receive 49,825.61 sUSDC \(1,000/0.020070\).

A few months later, you decide it’s time to withdraw your USDC from the protocol; the exchange rate is now 0.021591:

* Your 49,825.61 sUSDC is now equal to 1,075.78 USDC \(49,825.61 \* 0.021591\)
* You could withdraw 1,075.78 USDC, which would redeem all 49,825.61 sUSDC
* Or, you could withdraw a portion, such as your original 1,000 USDC, which would redeem 46,315.59 sUSDC \(keeping 3,510.01 sUSDC in your wallet\)

## How do I view my sTokens?

Each sToken is visible on [Etherscan](https://etherscan.io/tokens/label/strike), and you should be able to view them in the list of tokens associated with your address

sToken balances have been integrated into [Coinbase Wallet](https://itunes.apple.com/us/app/coinbase-wallet/id1278383455) and MetaMask; other wallets may add sToken support

## Can I transfer sTokens?

Yes, but exercise caution! By transferring sTokens, you’re transferring your balance of the underlying asset inside the Strike protocol. If you send a sToken to your friend, your balance \(viewable in the [Strike Interface](https://app.strike.org/)\) will decline, and your friend will see their balance increase.

A sToken transfer will fail if the account has [entered](../comptroller/enter-markets.md) that sToken market and the transfer would have put the account into a state of negative [liquidity](../comptroller/get-account-liquidity.md).

