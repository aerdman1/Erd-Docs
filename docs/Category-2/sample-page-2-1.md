---
title: Sample Page 2
deprecated: false
---
# 📚 ReadMe.io End User Login Process

***

## 1. Authentication Method: SAML SSO vs ReadMe Authentication

* **Is SAML SSO enabled?**
  * ✅ **Yes:** Use **SAML SSO Flow** (authentication is handled by your Identity Provider).
    * Optionally, **Group Mapping** (if configured) can automatically assign roles/permissions.
  * ❌ **No:** Use **ReadMe Authentication Flow** (ReadMe handles login directly).

***

## 2. Access Eligibility (ReadMe Authentication Only)

* **Are self sign-ups enabled?**
  * ✅ **Yes:** Proceed to **New User Access Rules** (below).
  * ❌ **No:** Check if the user was **directly invited**.
    * ✅ **Invited:** Proceed with login.
    * ❌ **Not Invited:** Deny access.

***

## 3. New User Access Rules (ReadMe Authentication Only)

### Key Settings: **Manual Approval vs Automatic Access**

* Applies to **new external End Users signing up**.
* This does **not** affect SAML SSO users if Group Mapping is in place (their permissions are mapped via SAML groups instead).

| Setting              | Description                                                                                  |
| -------------------- | -------------------------------------------------------------------------------------------- |
| **Manual Approval**  | All new users need to be manually approved in **End User Management** before gaining access. |
| **Automatic Access** | All new users are automatically given the **default permission level** (e.g., Viewer).       |

***

## 4. Domain Safelist Rules (Optional, ReadMe Authentication Only)

* If a **Domain Safelist** is set up, the **New User Access Rules** apply only to users with **email domains matching the safelist**.
* Users **outside the safelist domains** always require **manual approval**, regardless of the New User Access setting.

| Setting              | Domain Match?      | Access Behavior                                         |
| -------------------- | ------------------ | ------------------------------------------------------- |
| **Manual Approval**  | ✅ Matches safelist | Needs manual approval                                   |
| **Manual Approval**  | ❌ Not on safelist  | Needs manual approval                                   |
| **Automatic Access** | ✅ Matches safelist | Automatically granted default permission (e.g., Viewer) |
| **Automatic Access** | ❌ Not on safelist  | Needs manual approval                                   |

***

## 5. Passwordless Login Rules (ReadMe Authentication Only)

After eligibility is confirmed (either via sign-up or invitation), **Passwordless Login Setting** applies:

| Setting     | Behavior                                                                 |
| ----------- | ------------------------------------------------------------------------ |
| **Always**  | Force passwordless login (magic link via email).                         |
| **Default** | User chooses between **passwordless login** or **password-based login**. |
| **Never**   | Force traditional **password-based login**.                              |

***

## ✅ Summary Decision Path

| Step                                                 | Options                                                            |
| ---------------------------------------------------- | ------------------------------------------------------------------ |
| **1. Authentication Method**                         | SAML SSO or ReadMe Authentication                                  |
| **2. Access Eligibility (if ReadMe Authentication)** | Self sign-up enabled, invited-only, or denied                      |
| **3. New User Access Control (if applicable)**       | Manual Approval or Automatic Access for safelisted users           |
| **4. Passwordless Mode (if ReadMe Authentication)**  | Always Passwordless, Default (User Chooses), or Never Passwordless |

***

## 📝 Example Scenarios

### Example 1: SAML SSO enabled, with Group Mapping

* User authenticates via Identity Provider (IdP).
* If **Group Mapping** is configured, ReadMe assigns roles/permissions based on the IdP group membership.

***

### Example 2: ReadMe Authentication, self sign-up enabled, no domain safelist

* New users can sign up.
* All new users either:
  * Require **manual approval**, or
  * Are automatically assigned the **default role**, depending on the **New User Access Setting**.
* Once approved, they log in based on the **Passwordless Login Setting**.

***

### Example 3: ReadMe Authentication, self sign-up enabled, domain safelist present

* Users with **approved domains**:
  * Follow the **New User Access Setting** (Automatic Access or Manual Approval).
* Users with **non-matching domains**:
  * Always require **manual approval**, regardless of the New User Access Setting.

***

### Example 4: ReadMe Authentication, self sign-up disabled, user invited

* Only pre-invited users can log in.
* Login method (passwordless vs. password-based) follows the **Passwordless Login Setting**.

***