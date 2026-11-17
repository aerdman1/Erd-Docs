---
title: Authentication
excerpt: Authenticate with an API key, or with OAuth 2.0 when you act for a team.
deprecated: false
hidden: false
icon: fad fa-key
metadata:
  robots: index
---
Every Orbit request is authenticated. Pick the method that fits how your integration runs.

<Tabs>
  <Tab title="API key" icon="fa-key">
    Send your secret key in the `X-Orbit-Key` header. This is the quickest way to start, and it suits scripts and back-end services.

    ```shell
    curl "https://api.us-east.orbit.erdman.example/v1/account/usage" \
      -H "X-Orbit-Key: ok_test_4eC39HqLyjWDarjtT1zdp7dc"
    ```

    | Prefix     | Mode | Charges your card |
    | :--------- | :--- | :---------------- |
    | `ok_test_` | Test | Never             |
    | `ok_live_` | Live | Yes               |
  </Tab>

  <Tab title="OAuth 2.0" icon="fa-shield-check">
    Use the **client credentials** flow when your platform books launches for a team. Trade your client ID and secret for a short-lived token:

    ```shell
    curl -X POST "https://auth.orbit.erdman.example/oauth/token" \
      -d grant_type=client_credentials \
      -d client_id=$ORBIT_CLIENT_ID \
      -d client_secret=$ORBIT_CLIENT_SECRET \
      -d scope="bookings:read bookings:write"
    ```

    Then send it as a bearer token: `Authorization: Bearer <token>`. Tokens last one hour.
  </Tab>
</Tabs>

## Scopes

OAuth tokens only reach what their scopes allow. API keys have every scope.

| Scope            | Lets you                                   |
| :--------------- | :----------------------------------------- |
| `bookings:read`  | List and read bookings                     |
| `bookings:write` | Create, change and cancel bookings         |
| `telemetry:read` | Read live telemetry for payloads in flight |

<Callout icon="❗️" theme="error">
  ### Never ship a secret key to a browser or an app

  Keys in front-end code can be read by anyone. If a key leaks, roll it under **Account → API keys**. The old key stops working right away.
</Callout>

<OrbitHelp />

<Accordion title="How this page is built" icon="fa-wand-magic-sparkles">
  * **Tabs** with Font Awesome icons, each holding code and a table
  * Two Markdown **tables**
  * An **error** Callout
  * The help box at the bottom is **reusable content**: one snippet, edited in one place, shown on many pages
  * The API Reference reads the same two auth methods from the OpenAPI file’s `securitySchemes`
</Accordion>
