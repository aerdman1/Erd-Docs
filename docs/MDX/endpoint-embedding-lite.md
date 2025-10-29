---
title: Endpoint Embedding Lite
deprecated: false
hidden: false
icon: far fa-arrows-maximize
metadata:
  robots: index
---
<EndpointEmbedLite
  endpoint="/pet"
  method="POST"
  title="Create Pet"
  displayMode="inline"
  apiBaseUrl="https://api.example.com"
/>

<EndpointEmbedLite
  endpoint="/user/{username}"
  method="GET"
  title="Get User"
  description="Retrieve a user by username."
/>

<EndpointEmbedLite
  endpoint="/pet/{id}"
  method="PUT"
  title="Update Pet"
  description="Update an existing pet’s information."
  apiBaseUrl="https://api.example.com"
/>

<EndpointEmbedLite
  endpoint="/pet/{id}"
  method="PATCH"
  title="Partially Update Pet"
  description="Update part of a pet record."
  apiBaseUrl="https://api.example.com"
/>

<EndpointEmbedLite
  endpoint="/pet/{id}"
  method="DELETE"
  title="Delete Pet"
  description="Remove a pet from the database."
  apiBaseUrl="https://api.example.com"
/>

<EndpointEmbedLite
  endpoint="/options"
  method="OPTIONS"
  title="Get Allowed Methods"
  description="View supported HTTP methods for a resource."
  apiBaseUrl="https://api.example.com"
/>
