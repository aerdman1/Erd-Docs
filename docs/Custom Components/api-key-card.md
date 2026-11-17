---
title: API Key Card
excerpt: Shows signed-in readers their own API key.
deprecated: false
hidden: false
icon: fad fa-key
metadata:
  robots: index
---
Signed-in readers see their own key, masked until they reveal it. Signed-out readers get a **Log in** button, and anyone can preview the card with a demo key.

<ApiKeyCard />

## Where the key comes from

Every custom component can read the signed-in reader’s login data as `user`. When the login sends an `apiKey` field, through a JWT, SAML or the Personalized Docs webhook, the card shows it. The same login data fills in Try It in the [API Reference](/reference/listlaunches).

```jsx
const key = 'apiKey' in user ? user.apiKey : '';
```

<Callout icon="⚠️" theme="warn">
  Check for a field with `in`. A missing field on `user` returns the field’s name in capitals, not `undefined`.
</Callout>

## Use it

```mdx
<ApiKeyCard field="apiKey" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `field` | Text | Which login field holds the key. Defaults to `apiKey`. |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * Nothing is fetched: the key is already on the page for the signed-in reader, and only they can see it.
  * **Copy** works inside ReadMe’s editor preview too.
</Accordion>
