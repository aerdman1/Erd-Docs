---
title: Table
deprecated: false
hidden: false
metadata:
  robots: index
---
<TableTools />

<br />

| Endpoint      | Method | Description                          | Parameters                        | Response Format |
| ------------- | ------ | ------------------------------------ | --------------------------------- | --------------- |
| `/users`      | `GET`  | Retrieves a list of users            | `limit` (int), `offset` (int)     | JSON            |
| `/users/{id}` | `GET`  | Retrieves details of a specific user | `id` (UUID)                       | JSON            |
| `/users`      | `POST` | Creates a new user                   | `name` (string), `email` (string) | JSON            |