---
title: Turbo Table
deprecated: false
hidden: false
metadata:
  robots: index
---
| Endpoint           | Method   | Description                          | Parameters                        | Response Format |
| ------------------ | -------- | ------------------------------------ | --------------------------------- | --------------- |
| `/users`           | `GET`    | Retrieves a list of users            | `limit` (int), `offset` (int)     | JSON            |
| `/users/{id}`      | `GET`    | Retrieves details of a specific user | `id` (UUID)                       | JSON            |
| `/users`           | `POST`   | Creates a new user                   | `name` (string), `email` (string) | JSON            |
| `/users/{id}`      | `PUT`    | Updates a user's details             | `id` (UUID), `name`, `email`      | JSON            |
| `/users/{id}`      | `DELETE` | Deletes a user                       | `id` (UUID)                       | JSON            |
| `/orders`          | `GET`    | Retrieves all orders                 | `limit`, `offset`                 | JSON            |
| `/orders/{id}`     | `GET`    | Retrieves details of an order        | `id` (UUID)                       | JSON            |
| `/orders`          | `POST`   | Creates a new order                  | `user_id`, `items`                | JSON            |
| `/orders/{id}`     | `PUT`    | Updates an order                     | `id` (UUID), `status`             | JSON            |
| `/orders/{id}`     | `DELETE` | Cancels an order                     | `id` (UUID)                       | JSON            |
| `/products`        | `GET`    | Retrieves a list of products         | `category`, `limit`               | JSON            |
| `/products/{id}`   | `GET`    | Retrieves product details            | `id` (UUID)                       | JSON            |
| `/products`        | `POST`   | Adds a new product                   | `name`, `price`, `category`       | JSON            |
| `/products/{id}`   | `PUT`    | Updates product information          | `id`, `name`, `price`             | JSON            |
| `/products/{id}`   | `DELETE` | Removes a product                    | `id` (UUID)                       | JSON            |
| `/categories`      | `GET`    | Retrieves all product categories     | None                              | JSON            |
| `/categories/{id}` | `GET`    | Retrieves category details           | `id` (UUID)                       | JSON            |
| `/categories`      | `POST`   | Creates a new category               | `name`                            | JSON            |
| `/categories/{id}` | `PUT`    | Updates category details             | `id`, `name`                      | JSON            |
| `/categories/{id}` | `DELETE` | Deletes a category                   | `id` (UUID)                       | JSON            |
| `/reviews`         | `GET`    | Retrieves all reviews                | `product_id`, `limit`             | JSON            |
| `/reviews/{id}`    | `GET`    | Retrieves a review's details         | `id` (UUID)                       | JSON            |