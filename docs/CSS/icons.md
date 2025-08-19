---
title: Icons
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---


# Using Icons in ReadMe

There are a few ways to include icons inline with your docs.

---

## 1. Inline Images (simplest)

Upload your icon (SVG/PNG) to ReadMe (or a hidden “Assets” page), then use Markdown image syntax.

```md
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices  
![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users
```

**Result:**
📱 Devices  👤 Users

---

## 2. Inline with Spacing

If they’re dropping to new lines, make sure there’s no blank line between them. You can also add spaces with `&nbsp;`:

```md
![](https://files.readme.io/devices.svg) Devices&nbsp;&nbsp;![](https://files.readme.io/users.svg) Users
```

**Result:**
📱 Devices  👤 Users

---

## 3. Styled Inline Icons

You can wrap them in `<span>` to adjust alignment:

```md
Click the 
<span style="display:inline-block; vertical-align:middle;">
  <img src="https://files.readme.io/users.svg" width="20" alt="Users">
</span> 
button to continue.
```

---

## 4. Emoji-style (Custom CSS)

ReadMe supports native emojis like `:rocket:` → 🚀, but custom icons can’t be added to the `:emoji:` system.

If you want them to behave more “emoji-like,” you could load your icons from a CDN and map them with CSS:

```html
<style>
.icon-users::before {
  content: url("https://files.readme.io/users.svg");
  display: inline-block;
  vertical-align: middle;
  margin: 0 4px;
}
</style>

<p>Click <span class="icon-users"></span> to open the Users panel.</p>
```

**Result:**
Click 👤 to open the Users panel.

---

## 5. External Libraries

If your product already has an icon library (like FontAwesome or your own design system), you can pull that in via a CDN:

```html
<link rel="stylesheet" href="https://cdn.example.com/icons.css" />
<p>Click <i class="icon-users"></i> to continue.</p>
```

---

### Takeaway

* ✅ **Easiest:** Upload icons as images and reference with Markdown.
* ✅ **Reusable/Emoji-like:** If you really want shorthand (`<span class="icon-users"></span>`), you’ll need to load your own CSS.
* ❌ Not recommended: making a Reusable Block per icon — too much overhead.

