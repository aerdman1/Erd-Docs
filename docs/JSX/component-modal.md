---
title: Component Modal
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
<ContentModal
  label="Transactions and accounting events details"
  title="Transactions and accounting events details"
  modalId="htmlTable2"
  size="xl"
  content={(
    <table border="1" cellSpacing="0" cellPadding="0">
      <thead>
        <tr>
          <th>Date</th>
          <th>Transaction type</th>
          <th>Event type</th>
          <th>Entry type</th>
          <th>Description</th>
          <th>Cycle stage</th>
          <th>When it happens</th>
          <th>What is accounted</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>1 July</td>
          <td>701</td>
          <td>701</td>
          <td>701</td>
          <td>Refinancing credit</td>
          <td>Contract</td>
          <td>Refinancing credit: transaction creation</td>
          <td>Principal amount</td>
        </tr>
      </tbody>
    </table>
  )}
/>
