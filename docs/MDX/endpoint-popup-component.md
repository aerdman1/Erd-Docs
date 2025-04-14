---
title: Endpoint Popup
deprecated: false
hidden: false
metadata:
  robots: index
---
## API Endpoint Popup Examples

### Popup Version (Link)

When you want to keep your page uncluttered, you can use the "popup" display mode. In this mode, the endpoint is shown as a hyperlink. When a user hovers over this <EndpointPopup endpoint="/pet" specFile="ErdSpec1.json" linkText="Pet Endpoint" />, it displays detailed information about the endpoint in a popup.

Hover over the link above to see a quick summary, description, and an example response for the `/pet` endpoint. This version is ideal if you want to provide more context only when needed.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.

Another example is <EndpointPopup endpoint="/pet/findByStatus" specFile="ErdSpec1.json" linkText="Find Pets by Status" />, which lets you dynamically look up pets based on availability (e.g. `available`, `pending`, `sold`). Hover to preview how this search works without cluttering the UI.

Want to find pets by tags instead? Try this: <EndpointPopup endpoint="/pet/findByTags" specFile="ErdSpec1.json" linkText="Tag-Based Search" />. It’s helpful when you’re categorizing animals by metadata like breed or size.

Need to delete a pet? <EndpointPopup endpoint="/pet/{petId}" specFile="ErdSpec1.json" linkText="Delete Pet Endpoint" /> lets you see the exact method and parameters without overwhelming your layout.

***

### Inline Version

If you prefer to show the API details right away without requiring any interaction, you can set the component to the "inline" mode. This will render both the hyperlink and all the endpoint details directly on the page.

<EndpointPopup endpoint="/pet" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint" />

This inline display is great for showing users how to **update** or **create** a pet using the same `/pet` path but different methods (`PUT` vs `POST`).

***

You can also update pets using form fields like this:

<EndpointPopup endpoint="/pet/{petId}" specFile="ErdSpec1.json" displayMode="popup" linkText="Update Pet by ID" />

When your UI needs to send simple `name`/`status` form values instead of JSON, this endpoint supports that pattern.

***

And finally, image upload:

<EndpointPopup endpoint="/pet/{petId}/uploadImage" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />

This one uses a `multipart/form-data` payload to attach files to pet records.