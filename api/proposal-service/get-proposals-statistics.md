---
description: >-
  The proposals statistics API returns information about proposals count based
  on state.
---

# GET: /proposals/statistics

**ProposalStatisticsRequest**

This API has no request parameters.

**ProposalStatisticsResponse**

The API response contains the proposal counts for states.

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| ProposalStatisticsData | `data` | Proposal statistics data. |

**ProposalStatisticsData**

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `active` | Active proposal count |
| uint32 | `passed` | Passed proposal count |
| uint32 | `failed` | Failed proposal count |

