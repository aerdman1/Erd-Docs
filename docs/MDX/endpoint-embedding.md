---
title: Endpoint Embedding
deprecated: false
hidden: false
metadata:
  robots: index
---
Popup Mode

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc et mattis diam.  <EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Pet Endpoint" displayMode="popup" /> Donec finibus eu sapien vel vulputate. Nam est tortor, posuere vitae blandit a, ultricies semper diam. Proin sed metus et tellus imperdiet ultrices sit amet a justo. Mauris mattis enim ac nisi tincidunt, et scelerisque urna pellentesque. Curabitur vitae dapibus ligula. Mauris ornare ullamcorper diam a vestibulum. Praesent suscipit purus id arcu volutpat suscipit. Renders a clickable label. On hover, a card appears with endpoint details.

On hover, a card appears with endpoint details. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc et mattis diam. <EndpointEmbed endpoint="/pet" method="PUT" specFile="ErdSpec1.json" linkText="Full Details" displayMode="popup" websiteBaseUrl="https://erdtest123.readme.io" apiTargetUrl="https://api.erdman.com" theme="endpoint-block" labels={true} show={{  
    summary: true,  
    description: true,  
    parameters: true,  
    tags: true,  
    requestBody: true,  
    responses: true,  
    security: true,  
    example: true,  
    readmeUrl: true,  
    apiUrl: true  
  }} /> - Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc et mattis diam. Praesent suscipit purus id arcu volutpat suscipit. Renders a clickable label. On hover, a card appears with endpoint details. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nunc et mattis diam.

***

## 📄 Inline Mode

Renders the full endpoint card directly in the page.

<Columns layout="auto">
  <Column>
    #### Block version:

    <EndpointEmbed theme="endpoint-block" endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" />
  </Column>

  <Column>
    #### Simple version:

    <EndpointEmbed theme="simple" endpoint="/pet" method="PUT" specFile="ErdSpec1.json" displayMode="inline" />
  </Column>
</Columns>

<br />

<br />

***

#### Full version:

<EndpointEmbed
  endpoint="/pet"
  method="POST"
  specFile="ErdSpec1.json"
  displayMode="inline"
  apiTargetUrl="https://example.com"
  linkText="Custom Label (POST)"
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

## 🗂️ Multiple Spec Files

Swap `specFile` to pull from different OpenAPI files:

<EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" linkText="List Users (NovaTest)" />

<EndpointEmbed
  endpoint="/v1/users"
  method="POST"
  specFile="NovaTest.json"
  websiteBaseUrl="https://erdtest123.readme.io"
  apiTargetUrl="https://api.novatest.com"
  displayMode="inline"
  linkText="Create User (NovaTest)"
  theme="simple"
  labels={true}
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

***

# Advanced Usage

## 🧱 In Cards

<Cards columns={2}>
  <Card title="User Management" icon="fa-user-cog">
    <EndpointEmbed endpoint="/v1/users" method="GET" specFile="NovaTest.json" displayMode="inline" theme="simple" linkText="List Users" show={{ summary: true, description: true, readmeUrl: true, apiUrl: true }} />
  </Card>

  <Card title="Posts API" icon="fa-file-alt">
    <EndpointEmbed endpoint="/v1/posts" method="POST" specFile="NovaTest.json" displayMode="inline" theme="simple" linkText="Create Post" show={{ summary: true, description: true, readmeUrl: true, apiUrl: true }} />
  </Card>
</Cards>

***

## 🔽 In Accordions

<Accordion title="Upload a Pet Image" icon="fa-image">
  <EndpointEmbed endpoint="/pet/{petId}/uploadImage" method="POST" specFile="ErdSpec1.json" displayMode="inline" linkText="Upload Pet Image" show={{ summary: true, description: true, readmeUrl: true, apiUrl: true }} />
</Accordion>

<Accordion title="Delete Pet by ID" icon="fa-trash">
  <EndpointEmbed endpoint="/pet/{petId}" method="DELETE" specFile="ErdSpec1.json" displayMode="inline" linkText="Delete Pet" show={{ summary: true, description: true, readmeUrl: true, apiUrl: true }} />
</Accordion>

***

## ➗ In Columns

<Columns layout="auto">
  <Column>
    <EndpointEmbed endpoint="/pet/findByTags" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Tags" show={{ summary: true, description: true, readmeUrl: false, apiUrl: true }} />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/findByTags" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Tags" show={{ summary: true, description: true, readmeUrl: false, apiUrl: true }} />
  </Column>

  <Column>
    <EndpointEmbed endpoint="/pet/findByTags" method="GET" specFile="ErdSpec1.json" displayMode="inline" linkText="Find by Tags" show={{ summary: true, description: true, readmeUrl: false, apiUrl: true }} />
  </Column>
</Columns>

<Accordion title="All props/default values">
  | **Prop**           | **Type**  | **Default**                 | **Description**                                                                            |
  | ------------------ | --------- | --------------------------- | ------------------------------------------------------------------------------------------ |
  | `websiteBaseUrl`   | `string`  | `'https://yourdocsite.com'` | The ReadMe project base URL (used for linking to reference pages).                         |
  | `apiTargetUrl`     | `string`  | *none*                      | Optional override for the real API server base URL (for displaying API URL).               |
  | `endpoint`         | `string`  | *required*                  | The API path you want to display (e.g. `/pet/{petId}`).                                    |
  | `method`           | `string`  | *optional*                  | The HTTP method (e.g. `GET`, `POST`). If omitted, auto-selects best match.                 |
  | `specFile`         | `string`  | *required*                  | The OpenAPI JSON file name to load (e.g. `ErdSpec1.json`).                                 |
  | `displayMode`      | `string`  | `'popup'`                   | Determines how the component renders: `'popup'` or `'inline'`.                             |
  | `linkText`         | `string`  | *fallbacks to`endpoint`*    | Custom text to display instead of the raw endpoint path.                                   |
  | `theme`            | `string`  | `'endpoint-block'`          | `'endpoint-block'` renders with background chrome; `'simple'` removes padding and borders. |
  | `labels`           | `boolean` | `true`                      | If `false`, hides labels like `Summary:`, `Parameters:`, etc.                              |
  | `show.summary`     | `boolean` | `true`                      | Toggles display of the summary/method line.                                                |
  | `show.description` | `boolean` | `true`                      | Toggles display of the endpoint description.                                               |
  | `show.parameters`  | `boolean` | `true`                      | Toggles display of parameter names.                                                        |
  | `show.tags`        | `boolean` | `true`                      | Toggles display of OpenAPI tags.                                                           |
  | `show.requestBody` | `boolean` | `false`                     | Toggles request body presence indicator.                                                   |
  | `show.responses`   | `boolean` | `false`                     | Toggles list of response codes.                                                            |
  | `show.security`    | `boolean` | `false`                     | Toggles display of security scheme info.                                                   |
  | `show.example`     | `boolean` | `false`                     | Toggles display of a sample JSON response.                                                 |
  | `show.readmeUrl`   | `boolean` | `false`                     | Toggles display of the ReadMe reference doc URL.                                           |
  | `show.apiUrl`      | `boolean` | `false`                     | Toggles display of the full API call URL (with method and `apiTargetUrl`).                 |
</Accordion>