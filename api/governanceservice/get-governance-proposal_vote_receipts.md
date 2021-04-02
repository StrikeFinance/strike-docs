# GET: /governance/proposal\_vote\_receipts

**ProposalVoteReceiptRequest**

The request to the Proposal Vote Receipt API can specify a number of filters, such as which id to retrieve information about or which account.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Key</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">uint32</td>
      <td style="text-align:left"><code>proposal_id</code>
      </td>
      <td style="text-align:left">A proposal id to filter on, e.g.?proposal_id=23</td>
    </tr>
    <tr>
      <td style="text-align:left">bytes</td>
      <td style="text-align:left"><code>account</code>
      </td>
      <td style="text-align:left">Filter for proposals receipts for the given account</td>
    </tr>
    <tr>
      <td style="text-align:left">bool</td>
      <td style="text-align:left"><code>support</code>
      </td>
      <td style="text-align:left">
        <p>Filter for proposals receipts by for votes withsupport=true</p>
        <p>or against votes withsupport=false</p>
        <p>. If support not specified, response will return paginated votes for both
          for and against votes</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">bool</td>
      <td style="text-align:left"><code>with_proposal_data</code>
      </td>
      <td style="text-align:left">
        <p>Will populate a proposal object on the vote receipt when request submitted
          withwith_proposal_data=true</p>
        <p>, default is false</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">uint32</td>
      <td style="text-align:left"><code>limit</code>
      </td>
      <td style="text-align:left">Number of proposal vote receipts to include in the response, default is
        100</td>
    </tr>
    <tr>
      <td style="text-align:left">uint32</td>
      <td style="text-align:left"><code>offset</code>
      </td>
      <td style="text-align:left">Pagination number for proposal vote receipts in the response, default
        is 0</td>
    </tr>
  </tbody>
</table>

**ProposalVoteReceiptResponse**

The Proposal Vote Receipt API returns a list of proposal vote receipts that match the given filters on the request

| Type | Key | Description |
| :--- | :--- | :--- |
| bool | `status` | If set false, indicates an error returning data. |
| ProposalVoteReceiptData | `data` | The list of proposal vote receipts matching the requested filter. |

**ProposalVoteReceiptData**

| Type | Key | Description |
| :--- | :--- | :--- |
| uint32 | `offset` | Offset of pagination |
| uint32 | `limit` | Limit of pagination |
| uint32 | `total` | Total count of matching data |
| ProposalVoteReceipt | `result` | The list of proposal vote receipts matching the requested filter |

**ProposalVoteReceipt**

| Type | Key | Description |
| :--- | :--- | :--- |
| uuid | `id` | Unique id for looking up a voteReceipt |
| string | `address` | The address that describes the proposer |
| bool | `hasVoted` | Flag that indicates voted |
| bool | `support` | Whether or not the voter supports the proposal |
| uint32 | `blockNumber` | Voted block number |
| uint32 | `blockTimestamp` | Voted block timestamp |
| string | `votes` | The number of votes cast by the voter |

