---
title: table
deprecated: false
hidden: false
metadata:
  robots: index
---
<Table>
  <thead>
    <tr>
      <th>
        Header name
      </th>

      <th>
        Description
      </th>

      <th>
        Required/Optional
      </th>

      <th>
        Values
      </th>
    </tr>
  </thead>

  <tbody>
    <tr>
      <td>
        Authorization
      </td>

      <td>
        Authorization security header
      </td>

      <td>
        Required
      </td>

      <td>
        `Bearer <Access token>`
      </td>
    </tr>

    <tr>
      <td>
        X-Client-Id
      </td>

      <td>
        Client ID
      </td>

      <td>
        Required
      </td>

      <td>
        `<Client ID>`
      </td>
    </tr>

    <tr>
      <td>
        Content-Type
      </td>

      <td>
        Format of the request body
      </td>

      <td>
        Required
      </td>

      <td>
        `application/json`
      </td>
    </tr>

    <tr>
      <td>
        sca-token
      </td>

      <td>
        SCA JWT bearer token:

        <br />

        In the sandbox environment, you can use a predefined test SCA JWT Bearer token (see the Prerequisites section).

        <br />

        In the live environment, you must create the token based on the message body (whose details are described below) and sign it with your private key. For more information on the token details, see the Appendix in Authentication guide.
      </td>

      <td>
        Required
      </td>

      <td>
        `<SCA Token>`
      </td>
    </tr>

    <tr>
      <td>
        Accept
      </td>

      <td>
        Format of the response body
      </td>

      <td>
        Required
      </td>

      <td>
        `application/json`
      </td>
    </tr>
  </tbody>
</Table>

<HTMLBlock>{`
<style>
table {
  display: block;
  overflow-x: auto;
  white-space: nowrap;
  max-width: 100%;
}
</style>
`}</HTMLBlock>