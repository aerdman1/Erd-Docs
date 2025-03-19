---
title: table
deprecated: false
hidden: false
metadata:
  robots: index
---
| Header name   | Description                         | Required/Optional | Values                  |
|--------------|---------------------------------|------------------|------------------------|
| Authorization | Authorization security header   | Required         | `Bearer <Access token>` |
| X-Client-Id   | Client ID                        | Required         | `<Client ID>`          |
| Content-Type  | Format of the request body       | Required         | `application/json`     |
| sca-token     | [SCA JWT bearer token](https://developer.pagonxtpayments.com/v1/docs/authentication-guide) | Required | `<SCA Token>` |
| Accept        | Format of the response body      | Required         | `application/json`     |

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