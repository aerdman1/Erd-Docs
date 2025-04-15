---
title: Endpoint Embed
deprecated: false
hidden: false
metadata:
  robots: index
---
## Popup (hover over)

When you want to keep your page clean and uncluttered, the "popup" display mode is the perfect solution. In this mode, the endpoint appears as a simple hyperlink—like this <EndpointEmbed endpoint="/pet/findByStatus" method="GET" specFile="ErdSpec1.json" linkText="Find Pets by Status" displayMode="popup" show={{ summary: true, description: true, parameters: true, requestBody: true, responses: true, security: true, tags: true, example: false }} />—and when users hover over it, a card pops up, revealing a concise summary and description of the endpoint. It’s super easy to integrate and customize, letting you provide just the right amount of detail without overwhelming your readers. Whether you're showcasing search capabilities or guiding users through your API, this approach makes your documentation interactive and engaging.

<br />

***

## Inline (directly on the page)

Here's a simple inline demo using a different endpoint. For example, this component renders the details for the User Login endpoint directly in the page flow:

<EndpointEmbed endpoint="/user/login" method="GET" specFile="ErdSpec1.json" linkText="User Login" displayMode="inline" show={{ summary: true, description: true, parameters: true, requestBody: true, responses: false, security: true, tags: true, example: true }} />

If you want all endpoint information to be immediately visible without any user interaction, "inline" mode is a great choice. This demo keeps it simple and focuses on a real-world endpoint in your API.

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

| Prop Name       | Type   | Default Value                                                                                                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------- | ------ | --------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **baseUrl**     | string | `'https://erdtest123.readme.io'`                                                                                                        | The base URL from which the OpenAPI spec will be fetched. This should point to your API or documentation host.                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **endpoint**    | string | *Required*                                                                                                                              | The API endpoint path (e.g., `/pet`, `/pet/findByStatus`) as defined in your OpenAPI spec.                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| **method**      | string | *Optional*                                                                                                                              | The HTTP method (e.g., `GET`, `POST`, `PUT`, `DELETE`). If provided, the component uses this specific method; otherwise, it selects one automatically (preferring one with an example).                                                                                                                                                                                                                                                                                                                                                              |
| **displayMode** | string | `'popup'` or `'inline'`                                                                                                                 | Determines how the endpoint details are shown. Use `"popup"` for a hover-triggered card, or `"inline"` to display details directly within the page flow.                                                                                                                                                                                                                                                                                                                                                                                             |
| **linkText**    | string | Defaults to the value of the `endpoint` prop                                                                                            | The text displayed as the hyperlink for the endpoint. If not provided, it will default to the endpoint path.                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **specFile**    | string | `"ErdSpec1.json"`                                                                                                                       | The filename of the OpenAPI specification. This file is fetched from `${baseUrl}/openapi/${specFile}`. Use a different filename if your spec is named differently.                                                                                                                                                                                                                                                                                                                                                                                   |
| **show**        | object | `{ summary: true, description: true, parameters: true, requestBody: true, responses: true, security: true, tags: true, example: true }` | An object that controls the visibility of various endpoint sections. Set each property to \`true\` to show, or \`false\` to hide. The available properties are: \<br>\`summary\` – Brief overview of the endpoint.\<br>\`description\` – Detailed description.\<br>\`parameters\` – List of parameters (query, path, header, etc.).\<br>\`requestBody\` – Payload details.\<br>\`responses\` – Response information.\<br>\`security\` – Authentication/authorization details.\<br>\`tags\` – Associated tags.\<br>\`example\` – An example response. |