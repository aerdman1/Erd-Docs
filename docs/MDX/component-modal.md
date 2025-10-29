---
title: Component Modal
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
# Input a custom HTML table

*Allows for any other content you wish to pop up in a modal

<ContentModal
  label="Open Example Modal"
  title="Example Modal"
  modalId="exampleModal"
  size="lg"
  content={
    <HTMLBlock>{`
      <table>
        <thead><tr><th>Column A</th><th>Column B</th></tr></thead>
        <tbody><tr><td>Value 1</td><td>Value 2</td></tr></tbody>
      </table>
    `}</HTMLBlock>
  }
/>

OR

# Use existing Markdown table

*This code will take any table DIRECTLY AFTER it and put it in a modal.

<ContentModal label="View table" title="Results" modalId="resultsTable" useNextTable TargetSelector=".rdmd-table-inner > table" />

| Test | Test | Test |
| :--- | :--- | :--- |
| Test | Test | Test |
| Test | Test | Test |

<br />

<br />
