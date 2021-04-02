# Timelock

Each sToken contract and the Comptroller contract allow the Timelock address to modify them. The Timelock contract can modify system parameters, logic, and contracts in a 'time-delayed, opt-out' upgrade pattern.

The Timelock has a hard-coded minimum delay of 2 days, which is the least amount of notice possible for a governance action. Each proposed action will be published at a minimum of 2 days in the future from the time of announcement. Major upgrades, such as changing the risk system, may have a 14 day delay.

The Timelock is controlled by the governance module; pending and completed governance actions can be monitored on the [Timelock Dashboard](https://app.strike.org/timelock).

