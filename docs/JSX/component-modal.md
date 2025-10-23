---
title: Component Modal
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
<br />

<ContentModal
  label="Open Example Modal"
  title="Example Modal Title (editable)"
  modalId="exampleModal"
  content={
    <>
      <p>This is just some plain text but you can add tables too:</p>
      <table border="1" cellSpacing="0" cellPadding="0">
        <thead>
          <tr>
            <th>Column A</th>
            <th>Column B</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>Value 1</td>
            <td>Value 2</td>
          </tr>
        </tbody>
      </table>
    </>
  }
/>
