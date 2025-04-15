---
title: Endpoint Embed
deprecated: false
hidden: false
metadata:
  robots: index
---
## 🔗 Popup Mode

When you want to keep your page uncluttered, use the "popup" display mode. The endpoint renders as a hyperlink—like this <EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="popup" />. When users hover over it, they’ll see a card with full details.

Another one: <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="popup" />—which lets you preview how the search works without cluttering your layout.

***

## 📦 Inline Mode

If you want all endpoint info to be immediately visible, `"inline"` mode will render the card directly in the flow of the page content.

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint (PUT)" />

<EndpointEmbed endpoint="/pet" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint (POST)" />

This is great when you're walking users through specific request/response flows.

***

## 🗂️ Works with Any Spec File

You can point to other OpenAPI files by changing the `specFile` prop. Useful if you’re documenting multiple services.

<EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users (NovaTest)" />

<EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User (NovaTest)" />

***

## 🧱 Inside Cards

This component plays nice inside ReadMe's `<Cards>` layout. Great for overview sections or dashboards.

<Cards columns={2}>
  <Card title="User Management" icon="fa-user-cog">
    <EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users" />

    <EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User" />
  </Card>

  <Card title="Posts API" icon="fa-file-alt">
    <EndpointEmbed endpoint="/v1/posts" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create Post" />

    <EndpointEmbed endpoint="/v1/posts/{postId}" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="Get Post by ID" />
  </Card>
</Cards>

***

## 🔽 Inside Accordions

Perfect for FAQs or progressive disclosure.

<Accordion title="Upload a Pet Image" icon="fa-image">
  <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
</Accordion>

<Accordion title="Delete Pet by ID" icon="fa-trash">
  <EndpointEmbed endpoint="/pet/{petId}" method="DELETE" specFile="ErdSpec1.json" displayMode="inline" linkText="Delete Pet" />
</Accordion>

***

## ➗ Inside Columns

Use `<Columns>` to organize multiple endpoints side by side.

<Columns layout="auto">
  <Column>
    <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Status" />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/findByTags" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Tags" />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Image" />
  </Column>
</Columns>