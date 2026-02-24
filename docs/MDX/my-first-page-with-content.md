---
title: My First Page with Content
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
| **PARAMETER** | **REQUIRED** | **DESCRIPTION** |
| --- | --- | --- |
| `client_id` | Required | The `client_id` you obtained in the Initial Setup. |
| `client_secret` | Required | The `client_secret` you obtained in the Initial Setup. |
| `grant_type` | Required | Must be _authorization_code_. |
| `code` | Required | The authorization code you retrieved in the previous step. |
| `redirect_uri` | Optional | Required if the `redirect_uri` parameter was included in the authorization request as described in [Section 1. Requesting authorization code](https://developers.wrike.com/oauth-20-authorization#requesting-auth-code), and the values must be identical. |