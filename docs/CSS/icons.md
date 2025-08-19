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

⚠️ **Note:** If you paste the same image using raw HTML (`<img>`), ReadMe will wrap it in a *lightbox* container (meant for screenshots). That’s why it may look bigger or styled differently. Markdown syntax (`![]()`) avoids the lightbox and is the best way to get “inline icon” behavior.

---

## 2. Inline with Spacing

If they’re dropping to new lines, make sure there’s no blank line between them. You can also add spaces with `&nbsp;`:

```md
![](https://files.readme.io/devices.svg) Devices&nbsp;&nbsp;![](https://files.readme.io/users.svg) Users
```

**Result:**
📱 Devices  👤 Users

---

## 3. Styled Inline Icons (with `<HTMLBlock>`)

If you need more control (e.g. alignment), you can use HTML inside a block:

```md
<HTMLBlock>{`
<p>
  Click the 
  <span style="display:inline-block; vertical-align:middle;">
    <img src="https://files.readme.io/users.svg" width="20" alt="Users" />
  </span> 
  button to continue.
</p>
`}</HTMLBlock>
```

**Result:**
Click 👤 button to continue.

---

## 4. Emoji-style (Custom CSS)

ReadMe supports native emojis like `:rocket:` → 🚀, but you can’t add custom icons to that system. If you want them to behave like emojis, you’d need to load them via CSS:

```html
<HTMLBlock>{`
<style>
.icon-users::before {
  content: url("https://files.readme.io/users.svg");
  display: inline-block;
  vertical-align: middle;
  margin: 0 4px;
}
</style>

<p>Click <span class="icon-users"></span> to open the Users panel.</p>
`}</HTMLBlock>
```

**Result:**
Click 👤 to open the Users panel.

---

## 5. External Libraries

If your product already has an icon library (like FontAwesome or your own set), you can pull that in via a CDN:

```html
<HTMLBlock>{`
<link rel="stylesheet" href="https://cdn.example.com/icons.css" />
<p>Click <i class="icon-users"></i> to continue.</p>
`}</HTMLBlock>
```

---

### Takeaway

* ✅ **Easiest:** Upload icons as images and reference with Markdown.
* ✅ **Reusable/Emoji-like:** Load them with CSS if you want `<span class="icon-users"></span>` shorthand.
* ❌ Not recommended: creating a Reusable Block per icon — too much overhead.
