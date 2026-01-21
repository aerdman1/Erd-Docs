---
title: Icons
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
(',')

## 1. Inline Images (simplest)

Upload your icon (SVG/PNG) to ReadMe (or a hidden “Assets” page), then use Markdown image syntax.

**EXAMPLE SYNTAX (for copy/paste):**

```
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices  
![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users
```

**Live Result in ReadMe:**
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices
![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users

⚠️ **Note:** These will inherently "stack" in ReadMe's editor due to how we handle images in the editor but on the public site, they will be side by side.

***

## 2. Inline with Spacing

If they’re dropping to new lines, make sure there’s no blank line between them. You can also add spaces with `&nbsp;`:

**EXAMPLE SYNTAX (for copy/paste):**

```
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices&nbsp;&nbsp;![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users
```

**Live Result in ReadMe:**
![](https://files.readme.io/ec086cdf823db1e0ed64d98c6c85dcd48fda2e0e85f020a1c48e19102d693c7e-devices.svg) Devices  ![](https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg) Users

***

## 3. Styled Inline Icons (with `<HTMLBlock>`)

If you need more control (e.g. alignment), wrap your HTML in a readme html block.

**EXAMPLE SYNTAX (for copy/paste):**

```html
<HTMLBlock>{`
<p>
  Click the 
  <span style="display:inline-block; vertical-align:middle;">
    <img src="https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg" width="20" alt="Users" />
  </span> 
  button to continue.
</p>
`}</HTMLBlock>
```

**Live Result in ReadMe:**

<HTMLBlock>{`
<p>
  Click the 
  <span style="display:inline-block; vertical-align:middle;">
    <img src="https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg" width="20" alt="Users" />
  </span> 
  button to continue.
</p>
`}</HTMLBlock>

<br />

***

## 4. Emoji-style (Custom CSS)

You can’t add custom icons to the built-in `:emoji:` system, but you can mimic it with CSS:

**EXAMPLE SYNTAX (for copy/paste):**

```html
<HTMLBlock>{`
<style>
.icon-users::before {
  content: url("https://files.readme.io/3df2652b3ae372a16f17272613c0d7ca2c6495ed1eee7d209569c3860086ebd1-users.svg");
  display: inline-block;
  vertical-align: middle;
  margin: 0 4px;
}
</style>

<p>Click <span class="icon-users"></span> to open the Users panel.</p>
`}</HTMLBlock>
```

**Live Result in ReadMe:**

## 5. External Libraries (GOOGLE MATERIAL EXAMPLE)

If your product already has an icon library (like FontAwesome), pull it in with a CDN:

IN HEADER OF YOUR SITE:

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.11.3/font/bootstrap-icons.css" />
```

**SYNTAX FOR THE PAGE (for copy/paste):**

```html
<HTMLBlock>{`
<p>
  Click <i class="bi bi-people"></i> to continue.
</p>
`}</HTMLBlock>
```

**Live Result in ReadMe**

<HTMLBlock>{`
<p>
  Click <i class="material-icons">people</i> to continue.
</p>
`}</HTMLBlock>

<br />

## 5. Use our Built in Font-Awesome icons

```html
<i class="fa-solid fa-gear"></i>  
<i class="fa-solid fa-house"></i>  
<i class="fa-solid fa-cloud"></i>
```

<br />

<HTMLBlock>{`
<i class="fa-solid fa-gear"></i>  
<i class="fa-solid fa-house"></i>  
<i class="fa-solid fa-cloud"></i>
`}</HTMLBlock>

<br />

<br />

### Takeaway

* ✅ **Easiest:** Upload icons as images and reference with Markdown.
* ✅ **Reusable/Emoji-like:** Load them with CSS if you want `<span class="icon-users"></span>` shorthand.
* ❌ Not recommended: creating a Reusable Block per icon — too much overhead.
