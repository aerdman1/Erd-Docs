---
title: Table Tool
deprecated: false
hidden: false
metadata:
  robots: index
---
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Duis in nisi in tortor malesuada scelerisque eu mollis ex.

<br />

| Endpoint         | Method   | Description                              | Parameters                            | Response Format |
| ---------------- | -------- | ---------------------------------------- | ------------------------------------- | --------------- |
| `/users`         | `GET`    | Retrieves a list of users                | `limit` (int), `offset` (int)         | JSON            |
| `/users/{id}`    | `GET`    | Retrieves details of a specific user     | `id` (UUID)                           | JSON            |
| `/users`         | `POST`   | Creates a new user                       | `name` (string), `email` (string)     | JSON            |
| `/users/{id}`    | `PUT`    | Updates user details                     | `id` (UUID), `name` (string)          | JSON            |
| `/users/{id}`    | `DELETE` | Deletes a user                           | `id` (UUID)                           | JSON            |
| `/auth/login`    | `POST`   | Authenticates a user and returns a token | `email` (string), `password` (string) | JSON            |
| `/auth/logout`   | `POST`   | Logs out a user                          | `token` (string)                      | JSON            |
| `/products`      | `GET`    | Retrieves a list of products             | `category` (string), `limit` (int)    | JSON            |
| `/products/{id}` | `GET`    | Retrieves details of a specific product  | `id` (UUID)                           | JSON            |
| `/orders`        | `POST`   | Creates a new order                      | `user_id` (UUID), `items` (array)     | JSON            |

<br />

| ID | Name               | Type      | Description                                                    |
| -- | ------------------ | --------- | -------------------------------------------------------------- |
| 1  | UserID             | String    | Unique identifier for the user                                 |
| 2  | Email              | String    | Email address of the user                                      |
| 3  | CreatedAt          | Timestamp | Date and time the user was created                             |
| 4  | UpdatedAt          | Timestamp | Date and time the user was last updated                        |
| 5  | Role               | String    | Role assigned to the user                                      |
| 6  | Username           | String    | User's chosen display name                                     |
| 7  | FirstName          | String    | User's first name                                              |
| 8  | LastName           | String    | User's last name                                               |
| 9  | DateOfBirth        | Date      | User's date of birth                                           |
| 10 | PhoneNumber        | String    | User's contact phone number                                    |
| 11 | Address            | String    | User's mailing address                                         |
| 12 | City               | String    | City of the user's residence                                   |
| 13 | State              | String    | State of the user's residence                                  |
| 14 | Country            | String    | Country of the user's residence                                |
| 15 | PostalCode         | String    | User's postal code                                             |
| 16 | ProfilePictureURL  | String    | URL to the user's profile picture                              |
| 17 | Bio                | String    | Short biography of the user                                    |
| 18 | Website            | String    | User's personal or professional website                        |
| 19 | TwitterHandle      | String    | User's Twitter username                                        |
| 20 | LinkedInURL        | String    | URL to the user's LinkedIn profile                             |
| 21 | GitHubUsername     | String    | User's GitHub account username                                 |
| 22 | Company            | String    | User's current company affiliation                             |
| 23 | JobTitle           | String    | User's job title                                               |
| 24 | SubscriptionPlan   | String    | User's current subscription plan                               |
| 25 | SubscriptionStatus | String    | Status of the user's subscription                              |
| 26 | LastLoginAt        | Timestamp | Date and time the user last logged in                          |
| 27 | IsEmailVerified    | Boolean   | Indicates if the user's email is verified                      |
| 28 | IsPhoneVerified    | Boolean   | Indicates if the user's phone is verified                      |
| 29 | TwoFactorEnabled   | Boolean   | Indicates if two-factor authentication is enabled              |
| 30 | AccountStatus      | String    | Current status of the user's account (e.g., active, suspended) |