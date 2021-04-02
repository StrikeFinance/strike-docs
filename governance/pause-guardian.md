# Pause Guardian

The Comptroller contract designates a Pause Guardian address capable of disabling protocol functionality. Used only in the event of an unforeseen vulnerability, the Pause Guardian has one and only one ability: to disable a select set of functions: Mint, Borrow, Transfer, and Liquidate. The Pause Guardian cannot unpause an action, nor can it ever prevent users from calling Redeem, or Repay Borrow to close positions and exit the protocol.

STRK token-holders designate the Pause Guardian address, which is currently held by Strike Labs, Inc.

