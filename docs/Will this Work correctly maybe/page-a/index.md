---
title: test
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
<br />

Feature flags, also called feature toggles, permission toggles, or simply flags, let you turn certain functionality on and off without deploying code. They give you full control over the lifecycle of a feature. With feature flags, you can:

* Release code without exposing it to users by keeping the flag off.
* Gradually roll out a feature to a portion of your user base.
* Validate functionality and performance before a full release.

When a collaborator creates a flag, they are automatically assigned the **Admin** role for that flag.

## Permissions required to create a flag

To create a flag in Feature Experimentation, you must have access to an environment in the project.

When a collaborator creates a flag, they are automatically assigned the **Admin** role for that flag.

## Create a flag

### With the Feature Experimentation API

Use the [Create a New Flag](ref:create_flag) endpoint.

**Endpoint** –  `POST https://api.optimizely.com/flags/v1/projects/PROJECT_ID/flags`

**Authentication** – Include your API key in the `Authorization`  header as a Bearer token. See [Generate tokens and use the REST APIs](ref:generate-tokens-and-use-the-rest-apis).

**Request example**

> 📘 Note
>
> Replace placeholder text written in all caps with underscores with your information.

```curl
curl --request POST \
     --url https://api.optimizely.com/flags/v1/projects/PROJECT_ID/flags \
     --header 'accept: application/json' \
     --header 'content-type: application/json' \
     --header 'authorization: Bearer TOKEN' \
     --data '
{
  "outlier_filtering_enabled": BOOLEAN_VALUE,
  "description": "FLAG_DESCRIPTION",
  "key": "FLAG_KEY",
  "name": "FLAG_NAME"
}
'
```

**Response example**

```curl
{
  "key": "doc-test-flag",
  "name": "Doc test flag",
  "description": "Flag created via the API",
  "url": "/projects/PROJECT_ID/flags/doc-test-flag",
  "update_url": "/projects/PROJECT_ID/flags",
  "delete_url": "/projects/PROJECT_ID/flags/doc-test-flag",
  "archive_url": "/projects/PROJECT_ID/flags/archived",
  "variable_definitions": {},
  "environments": {
    "production": {
      "key": "production",
      "name": "Production",
      "enabled": false,
      "has_restricted_permissions": true,
      "priority": 1,
      "rules_summary": {},
      "rules_detail": [],
      "id": ENVIRONMENT_ID,
      "enable_url": "/projects/PROJECT_ID/flags/doc-test-flag/environments/production/ruleset/enabled",
      "created_time": "2025-04-14T19:48:26.000000Z"
    },
    "development": {
      "key": "development",
      "name": "Development",
      "enabled": false,
      "has_restricted_permissions": false,
      "priority": 2,
      "rules_summary": {},
      "rules_detail": [],
      "id": ENVIRONMENT_ID,
      "enable_url": "/projects/PROJECT_ID/flags/doc-test-flag/environments/development/ruleset/enabled",
      "created_time": "2025-04-14T19:48:26.000000Z"
    }
  },
  "id": ID,
  "urn": "flags.flags.optimizely.com::ID",
  "archived": false,
  "outlier_filtering_enabled": true,
  "project_id": PROJECT_ID,
  "created_by_user_id": "USER@optimizely.com",
  "created_by_user_email": "USER@optimizely.com",
  "account_id": ACCOUNT_ID,
  "role": "admin",
  "created_time": "2025-09-12T16:16:10.260857Z",
  "updated_time": "2025-09-12T16:16:10.260859Z",
  "revision": 1
}

```

See [Create a New Flag](ref:create_flag) API endpoint reference documentation for information on creating a flag with the Feature Experimentation API. You can also follow the [REST API cookbook](ref:set-up-visual-basic-to-run-rest-api-calls) and see [step one to create a flag](https://docs.developers.optimizely.com/feature-experimentation/recipes/1-create-a-flag-and-variables#/).

### With the Feature Experimentation UI

See [Create a flag](https://support.optimizely.com/hc/en-us/articles/38906082664077#h_01K230AWS1XDM92RASP2W5213P) in the user documentation for a step-by-step guide.

## Implement the feature flag

> 📘 Note
>
> Before implementing the flag, decide how to pass user identifiers to Feature Experimentation. This ensures each user has a consistent experience of the flag being on or off.
>
> See [Handle user ids](doc:handle-user-ids) for information.

After you create the flag in the Optimizely Feature Experimentation dashboard, you need to integrate it with your application code. Use the `Decide` method to enable or disable the flag for a user.

```csharp
// Decide if user sees a feature flag variation
var user = optimizely.CreateUserContext("user123", new UserAttributes { { "logged_in", true } });
var decision = user.Decide("flag_1");
var enabled = decision.Enabled;
```
```go
// Decide if user sees a feature flag variation
user := optimizely.CreateUserContext("user123", map[string]interface{}{"logged_in": true})
decision := user.Decide("flag_1", nil)
enabled := decision.Enabled
```
```dart Flutter
// Decide if user sees a feature flag variation
var user = await flutterSDK.createUserContext(userId: "user123");
var decideResponse = await user.decide("product_sort");
var enabled = decision.enabled;
```
```java
// Decide if user sees a feature flag variation
OptimizelyUserContext user = optimizely.createUserContext("user123", new HashMap<String, Object>() { { put("logged_in", true); } });
OptimizelyDecision decision = user.decide("flag_1");
Boolean enabled = decision.getEnabled();
```
```javascript
// Decide if user sees a feature flag variation
const user = optimizely.createUserContext('user123', { logged_in: true });
const decision = user.decide('flag_1');
const enabled = decision.enabled;
```
```php
// Decide if user sees a feature flag variation
$user = $optimizely->createUserContext('user123', ['logged_in' => true]);
$decision = $user->decide('flag_1');
$enabled = $decision->getEnabled();
```
```python
# Decide if user sees a feature flag variation
user = optimizely.create_user_context("user123", {"logged_in": True})
decision = user.decide("flag_1")
enabled = decision.enabled
```
```jsx React
// Decide if user sees a feature flag variation
var decision = useDecision('flag_1', null, { overrideUserAttributes: { logged_in: true }});
var enabled = decision.enabled;
```
```ruby
# Decide if user sees a feature flag variation
user = optimizely_client.create_user_context('user123', {'logged_in' => true})
decision = user.decide('flag_1')
decision.enabled
```
```swift
// Decide if user sees a feature flag variation
let user = optimizely.createUserContext(userId: "user123", attributes: ["logged_in":true])
let decision = user.decide(key: "flag_1")
let enabled = decision.enabled
```

For more detailed examples of each SDK, see the following:

* [Android SDK example usage](doc:example-usage-android)
* [Go SDK example usage](doc:example-usage-go)
* [C# SDK example usage](doc:example-usage-csharp)
* [Flutter SDK example usage](doc:example-usage-flutter)
* [Java SDK example usage](doc:example-usage-java)
* [JavaScript example usage](doc:example-usage-of-the-javascript-sdk) – SDK versions 6.0.0 and later.
* [Javascript (Browser) SDK example usage](doc:example-usage-javascript-prior-to-v6) – SDK versions 5.3.5 and earlier.
* [JavaScript (Node) SDK example usage](doc:example-usage-javascript-node-prior-to-v6) – SDK versions 5.3.5 and earlier.
* [PHP SDK example usage](doc:example-usage-php)
* [Python SDK example usage](doc:example-usage-python)
* [React SDK example usage](doc:example-usage-react)
* [React Native SDK example usage](doc:example-usage-reactnative)
* [Ruby SDK example usage](doc:example-usage-ruby)
* [Swift SDK example usage](doc:example-usage-swift)

Adapt the integration code in your application. Show or hide the flag's functionality for a given user ID based on the boolean value your application receives.

The [`Decide` method](doc:core-concepts-feature-experimentation#decide-methods) separates code deployment from the decision to show a feature. The flag's rules determine the result. For example, it returns false if the user is assigned to the control or "off" variation in an experiment.

## Next steps

To deliver feature flag configurations, see [Create flag variations](doc:create-flag-variations).
