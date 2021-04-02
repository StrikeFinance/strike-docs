# VoterService

The voter history service retrieves account and historical information about votes. You can use this API to find out the vote account or vote history.

```text
// Retreives a list of vote accounts
fetch("https://api.strike.org/api/voters/accounts");

// Retreives a detail information of vote account
fetch("https://api.strike.org/api/voters/accounts/:address");

// Retreives a history of vote account
fetch("https://api.strike.org/api/voters/history/:address");

// Retreives a vote data by proposal index
fetch("https://api.strike.org/api/voters/:proposalId");
```



