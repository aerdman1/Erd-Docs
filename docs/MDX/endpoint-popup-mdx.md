---
title: Endpoint Popup
deprecated: false
hidden: false
metadata:
  robots: index
---
## API Endpoint Popup Examples

### Popup Version (Link)

When you want to keep your page uncluttered, you can use the "popup" display mode. In this mode, the endpoint is shown as a hyperlink. When a user hovers over this <EndpointPopup endpoint="/pet" specFile="ErdSpec2.json" linkText="Pet Endpoint" />, it displays detailed information about the endpoint in a popup.

Hover over the link above to see a quick summary, description, and an example response for the `/pet` endpoint. This version is ideal if you want to provide more context only when needed.

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla.

Another example is <EndpointPopup endpoint="/findPetsByStatus" specFile="ErdSpec2.json" linkText="Find Pets by Status" />, which lets you dynamically look up pets based on availability (e.g. `available`, `pending`, `sold`). Hover to preview how this search works without cluttering the UI.

### Inline Version

If you prefer to show the API details right away without requiring any interaction, you can set the component to the "inline" mode. This will render both the hyperlink and all the endpoint details directly on the page. For example:

<EndpointPopup endpoint="/updatePet" specFile="ErdSpec2.json" displayMode="inline" />

With the inline version, readers see the complete endpoint information immediately. This is useful in sections where full details are critical to understanding the API behavior.

***

Curious about how new pets get added? Here's the endpoint that lets you do just that:

<EndpointPopup endpoint="/addPet" specFile="ErdSpec2.json" displayMode="inline" />

You can use it to add a brand new pet to the store. It supports a full JSON body with `id`, `name`, and `status`.

***

For more advanced filtering, check out <EndpointPopup endpoint="/findPetsByTags" specFile="ErdSpec2.json" linkText="Find Pets by Tags" />. This is a flexible way to query pets by specific tag values. It’s especially handy if you're managing metadata or categories.

***

Want to retrieve specific pet details? Here’s a simple one:

<EndpointPopup endpoint="/getPetById" specFile="ErdSpec2.json" displayMode="inline" />

This lets you get a single pet’s full record using its ID—ideal for profile pages or detail modals.

***

To update pet info using form data (instead of JSON), you can use this:

<EndpointPopup endpoint="/updatePetWithForm" specFile="ErdSpec2.json" displayMode="inline" />

This endpoint supports updates via form-encoded fields, which is useful in certain frontend form situations where JSON isn't ideal.

***

Need to remove a pet from the system? Just hover over this link: <EndpointPopup endpoint="/deletePet" specFile="ErdSpec2.json" linkText="Delete Pet Endpoint" />

The popup will explain how to use the `DELETE` method properly, and what to expect in terms of response codes.

***

Lastly, here’s an endpoint for uploading pet images:

<EndpointPopup endpoint="/uploadFile" specFile="ErdSpec2.json" displayMode="inline" />

This allows users to attach a photo to a pet record via multipart form upload.