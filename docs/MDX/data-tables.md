---
title: Data Tables
deprecated: false
hidden: false
metadata:
  robots: index
---
<DataTable />

<br />

| Endpoint      | Method | Description                          | Parameters                        | Response Format |
| ------------- | ------ | ------------------------------------ | --------------------------------- | --------------- |
| `/users`      | `GET`  | Retrieves a list of users            | `limit` (int), `offset` (int)     | JSON            |
| `/users/{id}` | `GET`  | Retrieves details of a specific user | `id` (UUID)                       | JSON            |
| `/users`      | `POST` | Creates a new user                   | `name` (string), `email` (string) | JSON            |

***NOTE: This is a preview table and will not be visible when the component is added to your live page.***