---
title: Endpoint Embed
deprecated: false
hidden: false
metadata:
  robots: index
---
# Basic Usage

## 🔗 Popup Mode

When you want to keep your page uncluttered, use the "popup" display mode. The endpoint renders as a hyperlink—like this:

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="popup" />

When users hover over it, they’ll see a full-detail card.

***

## 📦 Inline Mode

If you want all endpoint info immediately visible, `"inline"` mode renders the card directly in the page flow:

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint (PUT)" />

<EndpointEmbed endpoint="/pet" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint (POST)" />

<EndpointEmbed
  endpoint="/pet"
  method="POST"
  specFile="ErdSpec1.json"
  displayMode="inline"
  linkText="Inline Pet Endpoint (POST)"
  show={{ 
    summary: true, 
    description: true, 
    parameters: true, 
    requestBody: true, 
    responses: true, 
    security: true, 
    tags: true, 
    example: true 
  }}
/>

***

## 🗂️ Works with Any Spec File

Switch OpenAPI files by changing `specFile`. For example:

<EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users (NovaTest)" />

<EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User (NovaTest)" />

***

# Advanced Usage

## 🧱 Inside Cards

Embed this component within ReadMe's `<Cards>` layout:

<Cards columns={2}>
  <Card title="User Management" icon="fa-user-cog">
    <EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />

    <EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
  </Card>

  <Card title="Posts API" icon="fa-file-alt">
    <EndpointEmbed endpoint="/v1/posts" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create Post" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />

    <EndpointEmbed endpoint="/v1/posts/{postId}" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="Get Post by ID" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
  </Card>
</Cards>

***

## 🔽 Inside Accordions

Great for FAQs or progressive disclosure:

<Accordion title="Upload a Pet Image" icon="fa-image">
  <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
</Accordion>

<Accordion title="Delete Pet by ID" icon="fa-trash">
  <EndpointEmbed endpoint="/pet/{petId}" method="DELETE" specFile="ErdSpec1.json" displayMode="inline" linkText="Delete Pet" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
</Accordion>

***

## ➗ Inside Columns

Organize multiple endpoints side by side:

<Columns layout="auto">
  <Column>
    <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Status" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/findByTags" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Tags" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Image" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />
  </Column>
</Columns>