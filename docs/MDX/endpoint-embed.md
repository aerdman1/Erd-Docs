---
title: Endpoint Embed
deprecated: false
hidden: false
metadata:
  robots: index
---
## API Endpoint Popup Examples

### Popup mode

When you want to keep your page uncluttered, you can use the "popup" display mode. In this mode, the endpoint is shown as a hyperlink. When a user hovers over this <EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="popup" />, it displays detailed information about the endpoint in a popup.

Hover over the link above to see a quick summary, description, and an example response for the `/pet` endpoint. This version is ideal if you want to provide more context only when needed.

Another example is <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="popup" />, which lets you dynamically look up pets based on availability (e.g. `available`, `pending`, `sold`). Hover to preview how this search works without cluttering the UI.

### Inline mode

If you prefer to show the API details right away without requiring any interaction, you can set the component to the "inline" mode. This will render both the hyperlink and all the endpoint details directly on the page.

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint" />

This inline display is great for showing users how to **update** or **create** a pet using the same `/pet` path but different methods (`PUT` vs `POST`).

### Can use any spec file

<Cards columns={2}>
  <Card title="First Card" icon="fa-home" target="_blank">
    <EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users" />

    <EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User" />
  </Card>

  <Card title="Second Card" icon="fa-user">
    <EndpointEmbed endpoint="/v1/posts" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create Post" />

    <EndpointEmbed endpoint="/v1/posts/{postId}" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="Get Post by ID" />
  </Card>
</Cards>

<EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users" />

<EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User" />

<Columns layout="auto">
  <Column>
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload" />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload" />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload" />
  </Column>
</Columns>

<Cards columns={2}>
  <Card title="First Card" icon="fa-home" target="_blank">
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
  </Card>

  <Card title="Second Card" icon="fa-user">
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
  </Card>
</Cards>

<br />

<Accordion title="My Embedded Endpoint" icon="fa-info-circle">
  <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
</Accordion>