---
title: Endpoint Popup
deprecated: false
hidden: false
metadata:
  robots: index
---
## API Endpoint Popup Examples

### Popup Version (Link)

When you want to keep your page uncluttered, you can use the "popup" display mode. In this mode, the endpoint is shown as a hyperlink. When a user hovers over this <EndpointPopup endpoint="/pet" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="popup" />, it displays detailed information about the endpoint in a popup.

Hover over the link above to see a quick summary, description, and an example response for the `/pet` endpoint. This version is ideal if you want to provide more context only when needed.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.

Another example is <EndpointPopup endpoint="/pet/findByStatus" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="popup" />, which lets you dynamically look up pets based on availability (e.g. `available`, `pending`, `sold`). Hover to preview how this search works without cluttering the UI.

| Test | Test | Test |
| :--- | :--- | :--- |
| Test | Test | Test |
| Test | Test | Test |
| Test | Test | Test |
| Test | Test | Test |
| Test | Test | Test |

<Cards columns={2}>
  <Card title="First Card" icon="fa-home" target="_blank">
    <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
  </Card>

  <Card title="Second Card" icon="fa-user">
    <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
  </Card>
</Cards>

<Accordion title="Endpoint Testing" icon="fa-info-circle">
  <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
</Accordion>

<Accordion title="Endpoint Testing" icon="fa-info-circle">
  <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
</Accordion>

### Inline Version

If you prefer to show the API details right away without requiring any interaction, you can set the component to the "inline" mode. This will render both the hyperlink and all the endpoint details directly on the page.

<EndpointPopup endpoint="/pet" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint" />

This inline display is great for showing users how to **update** or **create** a pet using the same `/pet` path but different methods (`PUT` vs `POST`).

<br />

<Columns layout="auto">
  <Column>
    <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload" />
  </Column>

  <Column>
    <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload" />
  </Column>

  <Column>
    <EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload" />
  </Column>
</Columns>

# NOVA (a different spec)

<br />

<EndpointPopup endpoint="/v1/users" specFile="NovaTest.json" displayMode="inline" linkText="List Users" />

<br />

<EndpointPopup endpoint="/v1/users" specFile="NovaTest.json" displayMode="inline" linkText="Create User" />