---
title: Test1
deprecated: false
hidden: false
metadata:
  robots: index
---
Pure Markdown

| Data Type | Structure   | Code Snippet | Visual Reference | Description | Notes |
| --------- | ----------- | ------------ | ---------------- | ----------- | ----- |
| Text      | List item 1 | `test`       | Screenshot       | Explanation | Extra |
| Text      | List item 2 | `test`       | Screenshot       | Explanation | Extra |

<br />

HTML BLOCK

<HTMLBlock>{`
<table style="width:100%; border-collapse: collapse;">
  <thead>
    <tr style="background-color:#ddd;">
      <th style="border: 1px solid #000; padding: 8px;">Data Type</th>
      <th style="border: 1px solid #000; padding: 8px;">Structure</th>
      <th style="border: 1px solid #000; padding: 8px;">Code Snippet</th>
      <th style="border: 1px solid #000; padding: 8px;">Visual Reference</th>
      <th style="border: 1px solid #000; padding: 8px;">Description</th>
      <th style="border: 1px solid #000; padding: 8px;">Notes</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="border: 1px solid #000; padding: 8px;">Text</td>
      <td style="border: 1px solid #000; padding: 8px;">List item 1</td>
      <td style="border: 1px solid #000; padding: 8px;"><code>test</code></td>
      <td style="border: 1px solid #000; padding: 8px;">Screenshot</td>
      <td style="border: 1px solid #000; padding: 8px;">Explanation</td>
      <td style="border: 1px solid #000; padding: 8px;">Extra</td>
    </tr>
    <tr>
      <td style="border: 1px solid #000; padding: 8px;">Text</td>
      <td style="border: 1px solid #000; padding: 8px;">List item 2</td>
      <td style="border: 1px solid #000; padding: 8px;"><code>test</code></td>
      <td style="border: 1px solid #000; padding: 8px;">Screenshot</td>
      <td style="border: 1px solid #000; padding: 8px;">Explanation</td>
      <td style="border: 1px solid #000; padding: 8px;">Extra</td>
    </tr>
  </tbody>
</table>
`}</HTMLBlock>

<br />

JSX

\<table style=\{\{ width: "100%", borderCollapse: "collapse" }}>\
\<thead>
\<tr style=\{\{ backgroundColor: "#ddd" }}>
\<th style=\{\{ border: "1px solid #000", padding: "8px" }}>Data Type\</th>
\<th style=\{\{ border: "1px solid #000", padding: "8px" }}>Structure\</th>
\<th style=\{\{ border: "1px solid #000", padding: "8px" }}>Code Snippet\</th>
\<th style=\{\{ border: "1px solid #000", padding: "8px" }}>Visual Reference\</th>
\<th style=\{\{ border: "1px solid #000", padding: "8px" }}>Description\</th>
\<th style=\{\{ border: "1px solid #000", padding: "8px" }}>Notes\</th>
\</tr>
\</thead>

\<tbody>\
\<tr>
\<td style=\{\{ border: "1px solid #000", padding: "8px" }}>Text\</td>
\<td style=\{\{ border: "1px solid #000", padding: "8px" }}>List item 1\</td>
\<td style=\{\{ border: "1px solid #000", padding: "8px" }}>\\\<code>\\\</code>\</td>
\<td style=\{\{ border: "1px solid #000", padding: "8px" }}>Screenshot\</td>
\<td style=\{\{ border: "1px solid #000", padding: "8px" }}>Explanation\</td>
\<td style=\{\{ border: "1px solid #000", padding: "8px" }}>Extra\</td>
\</tr>

```
```