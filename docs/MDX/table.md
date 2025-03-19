---
title: table
deprecated: false
hidden: false
metadata:
  robots: index
---
<Table align={["left","left","left","left"]}>
  <thead>
    <tr>
      <th style={{ textAlign: "left" }}>
        Header name
      </th>

      <th style={{ textAlign: "left" }}>
        Description
      </th>

      <th style={{ textAlign: "left" }}>
        Required/Optional
      </th>

      <th style={{ textAlign: "left" }}>
        Values
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td style={{ textAlign: "left" }}>
        Authorization
      </td>

      <td class="scrollable-cell">
        Authorization security header
      </td>

      <td style={{ textAlign: "left" }}>
        Required
      </td>

      <td style={{ textAlign: "left" }}>
        `Bearer <Access token>`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        X-Client-Id
      </td>

      <td class="scrollable-cell">
        Client ID
      </td>

      <td style={{ textAlign: "left" }}>
        Required
      </td>

      <td style={{ textAlign: "left" }}>
        `<Client ID>`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Content-Type
      </td>

      <td class="scrollable-cell">
        Format of the request body
      </td>

      <td style={{ textAlign: "left" }}>
        Required
      </td>

      <td style={{ textAlign: "left" }}>
        `application/json`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        sca-token
      </td>

      <td class="scrollable-cell">
        SCA JWT bearer token:

        In the sandbox environment, you can use a predefined test SCA JWT Bearer token (see the Prerequisites section).

        In the live environment, you must create the token based on the message body (whose details are described below) and sign it with your private key. For more information on the token details, see the Appendix in Authentication guide.
      </td>

      <td style={{ textAlign: "left" }}>
        Required
      </td>

      <td style={{ textAlign: "left" }}>
        `<SCA Token>`
      </td>
    </tr>

    <tr>
      <td style={{ textAlign: "left" }}>
        Accept
      </td>

      <td class="scrollable-cell">
        Format of the response body
      </td>

      <td style={{ textAlign: "left" }}>
        Required
      </td>

      <td style={{ textAlign: "left" }}>
        `application/json`
      </td>
    </tr>
  </tbody>
</Table>

<HTMLBlock>{`
<style>
.rdmd-table table {
  table-layout: fixed; /* Fix column widths */
  width: 100%; /* Ensure the table does not expand beyond its container */
}

.rdmd-table th, .rdmd-table td {
  max-width: 200px; /* Restrict column width */
  word-wrap: break-word;
  overflow-wrap: break-word;
  word-break: break-word;
  vertical-align: top;
}

/* Enable ONLY vertical scrolling on long cells */
.scrollable-cell {
    max-height: 100px;
    overflow-y: auto;
    overflow-x: inherit;
    display: block;
    width: 100% !important;
    white-space: normal;
}

</style>
`}</HTMLBlock>