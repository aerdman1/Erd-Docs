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

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nisl ligula, facilisis ac ante quis, pellentesque maximus nulla. Etiam volutpat sem a nibh tempor, ac sollicitudin mauris ultrices. Vestibulum varius nisi ac leo consectetur pellentesque eu ut diam. Proin congue tempor urna id varius. Quisque fringilla erat nec nulla iaculis suscipit. Sed a mattis sapien. In dui arcu, facilisis quis finibus id, condimentum id ipsum. Suspendisse potenti.

### Inline Version

If you prefer to show the API details right away without requiring any interaction, you can set the component to the "inline" mode. This will render both the hyperlink and all the endpoint details directly on the page. For example:

<EndpointPopup endpoint="/pet" specFile="ErdSpec2.json" displayMode="inline" />

With the inline version, readers see the complete endpoint information immediately. This is useful in sections where full details are critical to understanding the API behavior.