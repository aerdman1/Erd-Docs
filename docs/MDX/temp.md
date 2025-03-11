---
title: Temp
deprecated: false
hidden: false
metadata:
  robots: index
---
# TOC

\[toc]

***

# [Admonition](pymdownx.tilde)

<br />

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

# pymdownx.tilde

~~Strikethrough~~

text~~subscript~~

***

# pymdownx.highlight

```python
# This is a test
print("Hello, world!")
```

```python

def hello_world():  
    print("Hello, world!") n

```

# pymdownx.inlinehilite

```python
If you see **different colors for keywords, comments, and strings**, **syntax highlighting is enabled**.

If everything is the **same color** and only has a gray background, ReadMe does not have syntax highlighting, and you may need a different approach (like a custom MDX component for code blocks).

INLINE: markdown_extensions:
  - pymdownx.highlight
  - pymdownx.inlinehilite
```

<br />

***

# pymdownx.snippets - DO NOT SUPPORT ATM :x:

***

# PXSPER :white_check_mark:

> ```python
> print("hello")
> ```

<br />

***

# pymdownx.superfences :white_check_mark:

<br />

> ```
> Code inside a blockquote
> ```

Normally, Markdown doesn’t allow this without escaping or additional indentation.

Would you like me to generate more test cases for ReadMe? 🚀

***

# pymdownx.emoji ✅

:+1: :smile: :volcano:

***

# pymdownx.tabbed  ❌ (we have tabs but not with this syntax)

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

# Details ❌ [https://facelessuser.github.io/pymdown-extensions/extensions/details/](https://facelessuser.github.io/pymdown-extensions/extensions/details/)

???+ note "Open styled details"

??? danger "Nested details!"\
And more content again.

***

# pymdownx.tasklist

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

# smarty ❌  [https://facelessuser.github.io/pymdown-extensions/extensions/smartsymbols/?h=](https://facelessuser.github.io/pymdown-extensions/extensions/smartsymbols/?h=)

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

# pymdownx.caret ❌ [https://facelessuser.github.io/pymdown-extensions/extensions/caret/](https://facelessuser.github.io/pymdown-extensions/extensions/caret/)

^^Insert me^^

H^2^0

text^a\ superscript^

***

# pymdownx.critic  [https://facelessuser.github.io/pymdown-extensions/extensions/critic/](https://facelessuser.github.io/pymdown-extensions/extensions/critic/)

\{++inserted text++}

<br />

\{--removed text--}

<br />

\{\~\~substituted text\~>replacement text\~\~}

<br />

\{==highlighted text==}

<br />

\{==highlighted text==}\{>>This is a comment on the highlighted text\<\<}

<br />

\{--

<br />

* removed item 1
  * removed item 2- removed sub-item
    * removed item 3

<br />

\--}

<br />

\{++

<br />

* added item 1
  * added item 2- added sub-item
    * added item 3

<br />

++}