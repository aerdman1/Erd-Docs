---
title: table
deprecated: false
hidden: false
metadata:
  robots: index
---
\<style>
.editor360-table \{
&#x20; display: block;
&#x20; overflow-x: auto;
&#x20; white-space: nowrap;
&#x20; max-width: 100%;
}
\</style>

\<div class="editor360-table">
&#x20;&#x20;
\| Header name   | Description                         | Required/Optional | Values                  |
\|--------------|---------------------------------|------------------|------------------------|
\| Authorization | Authorization security header   | Required         | \`Bearer \<Access token>\` |
\| X-Client-Id   | Client ID                        | Required         | \`\<Client ID>\`          |
\| Content-Type  | Format of the request body       | Required         | \`application/json\`     |
\| sca-token     | \[SCA JWT bearer token]\(https\://developer.pagonxtpayments.com/v1/docs/authentication-guide) | Required | \`\<SCA Token>\` |
\| Accept        | Format of the response body      | Required         | \`application/json\`     |

\</div>