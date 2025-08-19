---
title: Icons
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
Ah yep — that’s a ReadMe quirk. Their Markdown parser doesn’t like when we inline backticks and `{` inside the `<HTMLBlock>{` syntax.

To make it work:

* Don’t wrap the `<HTMLBlock>` itself in triple backticks.
* Inside examples, escape braces or just show them as plain text.

Here’s a fixed version you can paste directly into ReadMe without hitting that validation error.

---

# Using Icons in ReadMe

There are a few ways to include icons inline with your docs.

---

## 1. Inline Images (simplest)

Upload your icon (SVG/PNG) to ReadMe (or a hidden “Assets” page), then use Markdown image syntax.

```
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices  
![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users
```

**Result in ReadMe:**
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices
![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users

⚠️ **Note:** If you paste the same image using raw HTML (`<img>`), ReadMe will wrap it in a *lightbox* container (meant for screenshots). That’s why it may look bigger or styled differently. Markdown syntax (`![]()`) avoids the lightbox and is the best way to get “inline icon” behavior.

---

## 2. Inline with Spacing

```
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices&nbsp;&nbsp;![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users
```

**Result in ReadMe:**
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices  ![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users

---
