# GovernanceService

Note: This service is experimental \(alpha\) and subject to change.

The Governance Service includes three endpoints to retrieve information about STRK accounts, governance proposals, and proposal vote receipts. You can use the APIs below to pull data about the Strike governance system:

```text
  // Retreives a list of governance proposals
  fetch("https://api.strike.org/api/governance/proposals");
  
  // Retreives a list of governance proposal vote receipts
  fetch("https://api.strike.org/api/governance/proposal_vote_receipts");
  
  // Retreives a list of STRK accounts
  fetch("https://api.strike.org/api/governance/accounts");
```

{% page-ref page="get-governance-proposals.md" %}

{% page-ref page="get-governance-proposal\_vote\_receipts.md" %}

{% page-ref page="get-governance-accounts.md" %}

