---
title: Endpoint Embedding
deprecated: false
hidden: false
metadata:
  robots: index
---
# Basic Usage

## 💬 Popup Mode

#### Example with minimal props:

This uses the "popup" display mode. The endpoint renders as a hyperlink—like this: <EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="popup" /> When users hover over it, they’ll see a full-detail card.

#### Example with all props enabled:

<EndpointEmbed
  endpoint="/pet"
  method="PUT"
  specFile="ErdSpec1.json"
  linkText="Showing all props with a custom label"
  displayMode="popup"
  websiteBaseUrl="https://erdtest123.readme.io"
  apiTargetUrl="https://api.erdman.com"
  show={{
    summary: true,
    description: true,
    parameters: true,
    tags: true,
    requestBody: true,
    responses: true,
    security: true,
    example: false,
    readmeUrl: false,
    apiUrl: false
  }}
/>

This version includes all available options—description, parameters, request body, responses, tags, security, and more. It gives users the most complete view of the endpoint details.

***

## 📄 Inline Mode

If you want all endpoint info immediately visible, `"inline"` mode renders the card directly in the page flow:

#### Here is one with just a few props:

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" />

#### Here is one with all props enabled:

<EndpointEmbed
  endpoint="/pet"
  method="POST"
  specFile="ErdSpec1.json"
  displayMode="inline"
  apiTargetUrl="https://example.com"
  linkText="You can Override Link Text (POST)"
  show={{ 
    summary: true, 
    description: true, 
    parameters: true, 
    requestBody: true, 
    responses: true, 
    security: true, 
    tags: true, 
    example: true,
    readmeUrl: true,
    apiUrl: true
  }}
/>

***

## 🗂️ Works with Any Spec File

Switch OpenAPI files by changing `specFile`. For example:

<EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users (NovaTest)" />

<EndpointEmbed
  endpoint="/v1/users"
  method="POST"
  specFile="NovaTest.json"
  displayMode="inline"
  linkText="Create User (NovaTest)"
  show={{
    summary: true,
    description: true,
    parameters: true,
    requestBody: true,
    responses: true,
    security: true,
    tags: true,
    example: true,
    readmeUrl: false,
    apiUrl: true
  }}
/>

***

# Advanced Usage

## 🧱 Inside Cards

Embed this component within ReadMe's `<Cards>` layout:

<Cards columns={2}>
  <Card title="User Management" icon="fa-user-cog">
    <EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />

    <EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
  </Card>

  <Card title="Posts API" icon="fa-file-alt">
    <EndpointEmbed endpoint="/v1/posts" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create Post" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />

    <EndpointEmbed endpoint="/v1/posts/{postId}" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="Get Post by ID" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
  </Card>
</Cards>

***

## 🔽 Inside Accordions

Great for FAQs or progressive disclosure:

<Accordion title="Upload a Pet Image" icon="fa-image">
  <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
</Accordion>

<Accordion title="Delete Pet by ID" icon="fa-trash">
  <EndpointEmbed endpoint="/pet/{petId}" method="DELETE" specFile="ErdSpec1.json" displayMode="inline" linkText="Delete Pet" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
</Accordion>

***

## ➗ Inside Columns

Organize multiple endpoints side by side:

<Columns layout="auto">
  <Column>
    <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Status" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/findByTags" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Tags" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Image" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false, readmeUrl: true, apiUrl: true }} />
  </Column>
</Columns>