---
title: Plugins
deprecated: false
hidden: true
metadata:
  robots: index
---
<HTMLBlock>{`
<div class="rdmd-html">
<table>
<thead>
<tr>
<th><strong>Plugin</strong></th>
<th><strong>Support Status</strong></th>
<th><strong>Notes</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td><strong>Table of Contents (TOC)</strong></td>
<td>✅ ❓</td>
<td>Automatically supported via heading tags in ReadMe</td>
</tr>
<tr>
<td><strong>admonition</strong></td>
<td>❌ ✅</td>
<td>Can be mimicked via MDX components</td>
</tr>
<tr>
<td><strong>pymdownx.tilde</strong></td>
<td>✅ ✅</td>
<td>Strikethrough and subscript work</td>
</tr>
<tr>
<td><strong>pymdownx.highlight</strong></td>
<td>✅ ✅</td>
<td>Code block highlighting works</td>
</tr>
<tr>
<td><strong>pymdownx.inlinehilite</strong></td>
<td>✅ ✅</td>
<td>Inline syntax highlighting works</td>
</tr>
<tr>
<td><strong>pymdownx.snippets (Reusable Content)</strong></td>
<td>❌ ❌</td>
<td>No programmatic way to import reusable content</td>
</tr>
<tr>
<td><strong>pymdownx.superfences</strong></td>
<td>✅ ✅</td>
<td>Nested fenced blocks are supported</td>
</tr>
<tr>
<td><strong>pymdownx.emoji</strong></td>
<td>✅ ✅</td>
<td>GitHub-style <code>:emoji:</code> syntax works</td>
</tr>
<tr>
<td><strong>pymdownx.tabbed</strong></td>
<td>✅ ❓</td>
<td>We have a component for this, but not in their exact syntax</td>
</tr>
<tr>
<td><strong>Details (Collapsible Sections)</strong></td>
<td>❌ ✅</td>
<td>Requires a workaround</td>
</tr>
<tr>
<td><strong>pymdownx.tasklist</strong></td>
<td>✅ ✅</td>
<td>Task lists <code>[ ]</code> <code>[x]</code> are supported</td>
</tr>
<tr>
<td><strong>smarty</strong></td>
<td>❌ ✅</td>
<td>Needs a replacement or workaround</td>
</tr>
<tr>
<td><strong>pymdownx.caret</strong></td>
<td>❌ ✅</td>
<td>Requires a workaround for <code>&lt;ins&gt;</code> and <code>&lt;sup&gt;</code></td>
</tr>
<tr>
<td><strong>pymdownx.critic</strong></td>
<td>❌ ✅</td>
<td>Requires a workaround for Critic Markup</td>
</tr>
</tbody>
</table>
</div>
`}</HTMLBlock>

<br />

<br />

<br />

<br />

<br />

<HTMLBlock>{`
<style>
section.content-toc.grid-25 {
    display: inherit !important;
}
</style>
`}</HTMLBlock>

***

<br />

# TOC ✅:question:

## This is automatically supported via heading tags in ReadMe

## This will show up in your TOC

***

# admonition -  :x: :white_check_mark:

!!! note\
You should note that the title will be automatically capitalized.

!!! danger "Don't try this at home"\
This is a dangerous action. Proceed with caution.

!!! important ""\
This is an admonition box without a title.

MUST TRANSLATE TO:

<div class="admonition note">
  <p class="admonition-title">Note</p>
  <p>You should note that the title will be automatically capitalized.</p>
</div>

<div class="admonition danger">
  <p class="admonition-title">Don't try this at home</p>
  <p>This is a dangerous action. Proceed with caution.</p>
</div>

<div class="admonition important">
  <p>This is an admonition box without a title.</p>
</div>

***

# pymdownx.tilde ✅ ✅

~~Strikethrough~~

text~~subscript~~

***

# pymdownx.highlight ✅ ✅

```python
# This is a test
print("Hello, world!")
```

```python

def hello_world():  
    print("Hello, world!") n

```

# pymdownx.inlinehilite ✅ ✅

```python
If you see **different colors for keywords, comments, and strings**, **syntax highlighting is enabled**.

If everything is the **same color** and only has a gray background, ReadMe does not have syntax highlighting, and you may need a different approach (like a custom MDX component for code blocks).

INLINE: markdown_extensions:
  - pymdownx.highlight
  - pymdownx.inlinehilite
```

<br />

***

# pymdownx.snippets (Reusable Content) ❌ :x:

<HTMLBlock>{`
Single Line Format
Single line format is done by placing the following markup for the single line notation:


--8<-- "filename.ext"
`}</HTMLBlock>

<br />

***

# PXSPER  ✅ :white_check_mark:

> ```python
> print("hello")
> ```

<br />

***

# pymdownx.superfences ✅ :white_check_mark:

<br />

> ```
> Code inside a blockquote
> ```

Normally, Markdown doesn’t allow this without escaping or additional indentation.

Would you like me to generate more test cases for ReadMe? 🚀

***

# pymdownx.emoji ✅ ✅

:+1: :smile: :volcano:

***

# pymdownx.tabbed ✅:question: [https://facelessuser.github.io/pymdown-extensions/extensions/tabbed/](https://facelessuser.github.io/pymdown-extensions/extensions/tabbed/)

We have this as a Component

<HTMLBlock>{`
=== "Tab 1"
    Markdown **content**.

    Multiple paragraphs.

=== "Tab 2"
    More Markdown **content**.

    - list item a
    - list item b
`}</HTMLBlock>

***

# Details ❌ :white_check_mark: [https://facelessuser.github.io/pymdown-extensions/extensions/details/](https://facelessuser.github.io/pymdown-extensions/extensions/details/)

???+ note "Open styled details"

??? danger "Nested details!"\
And more content again.

***

# pymdownx.tasklist ✅ ✅

Task List

* [x] item 1
  * [x] item A
  * [ ] item B\
    more text
    * [x] item a
    * [ ] item b
    * [x] item c
  * [x] item C
* [ ] item 2
* [ ] item 3

***

# smarty ❌ :white_check_mark: [https://facelessuser.github.io/pymdown-extensions/extensions/smartsymbols/?h=](https://facelessuser.github.io/pymdown-extensions/extensions/smartsymbols/?h=)

(tm)\
(c)
(r)
c/o
+/-
\-->
\<--
\<-->
\=/=
1/4
1/2
3/4
1st
2nd
3rd

***

# pymdownx.caret :x: :white_check_mark: [https://facelessuser.github.io/pymdown-extensions/extensions/caret/](https://facelessuser.github.io/pymdown-extensions/extensions/caret/)

^^Insert me^^

H^2^0

text^a\ superscript^

***

# pymdownx.critic :x: :white_check_mark: [https://facelessuser.github.io/pymdown-extensions/extensions/critic/](https://facelessuser.github.io/pymdown-extensions/extensions/critic/)

<HTMLBlock>{`
Here is some {--*incorrect*--} Markdown.  I am adding this{++ here++}.  Here is some more {--text
 that I am removing--}text.  And here is even more {++text that I 
 am ++}adding.{~~

~>  ~~}Paragraph was deleted and replaced with some spaces.{~~  ~>

~~}Spaces were removed and a paragraph was added.

And here is a comment on {==some
 text==}{>>This works quite well. I just wanted to comment on it.<<}. Substitutions {~~is~>are~~} great!

General block handling.

{--

* test remove
* test remove
* test remove
    * test remove
* test remove

--}

{++

* test add
* test add
* test add
    * test add
* test add

++}
`}</HTMLBlock>