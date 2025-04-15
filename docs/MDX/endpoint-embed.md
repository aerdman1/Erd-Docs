---
title: Endpoint Embed
deprecated: false
hidden: false
metadata:
  robots: index
---
## Basic Usage

### Popup (hover over)

When you want to keep your page uncluttered, use the "popup" display mode. The endpoint renders as a hyperlink—like this <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="popup" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />.

***

<br />

### Inline (directly on the page)

<EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="inline" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />

If you want all endpoint info to be immediately visible, `"inline"` mode will render the card directly in the page flow. For example: <EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint (PUT)" />.

<EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="inline" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />

If you want all endpoint info to be immediately visible, `"inline"` mode will render the card directly in the page flow.

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" linkText="Inline Pet Endpoint (PUT)" />

***

## Advanced Usage

#### Deprecated

<EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="inline" show={{ summary: true, description: true, parameters: false, requestBody: false, responses: false, security: false, tags: false, example: false }} />

***

### 🗂️ Works with Any Spec File

You can point to other OpenAPI files by changing the `specFile` prop. Useful if you’re documenting multiple services.

<EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users (NovaTest)" />

<EndpointEmbed endpoint="/v1/users" method="POST" specFile="NovaTest.json" displayMode="inline" linkText="Create User (NovaTest)" />

***

### 🧱 Inside Cards

This component plays nicely inside ReadMe's `<Cards>` layout. Great for overview sections or dashboards.

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

### 🔽 Inside Accordions

Perfect for FAQs or progressive disclosure.

<Accordion title="Upload a Pet Image" icon="fa-image">
  <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" />
</Accordion>

<Accordion title="Delete Pet by ID" icon="fa-trash">
  <EndpointEmbed endpoint="/pet/{petId}" method="DELETE" specFile="ErdSpec1.json" displayMode="inline" linkText="Delete Pet" />
</Accordion>

***

### ➗ Inside Columns

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

&#x20;&#x20;

***

<HTMLBlock>{`
<style>
/* Skeleton Loading Styles */
.skeleton {
  width: 420px !important; /* Matches real cards */
  background: #f3f4f6;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  opacity: 0.7;
  min-height: 100px; /* Ensures same height as real cards */
}

.skeleton-method, .skeleton-title, .skeleton-path {
  background: linear-gradient(90deg, #e5e7eb 25%, #f3f4f6 50%, #e5e7eb 75%);
  background-size: 200% 100%;
  animation: shimmer 1.5s infinite linear;
  border-radius: 4px;
}
.skeleton-method {
  width: 50px;
  height: 12px;
  margin-bottom: 8px;
}
.skeleton-title {
  width: 60%;
  height: 16px;
  margin-bottom: 6px;
}
.skeleton-path {
  width: 80%;
  height: 12px;
}
@keyframes shimmer {
  0% { background-position: -200% 0; }
  100% { background-position: 200% 0; }
}

</style>
`}</HTMLBlock>