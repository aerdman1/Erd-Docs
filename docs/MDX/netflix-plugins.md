---
title: Netflix Plugins
deprecated: false
hidden: false
metadata:
  robots: index
---
<HTMLBlock>{`
<table data-start="63" data-end="1684"><thead data-start="63" data-end="125"><tr data-start="63" data-end="125"><th data-start="63" data-end="91"><strong data-start="65" data-end="75">Plugin</strong></th><th data-start="91" data-end="112"><strong data-start="93" data-end="111">Support Status</strong></th><th data-start="112" data-end="125"><strong data-start="114" data-end="123">Notes</strong></th></tr></thead><tbody data-start="188" data-end="1684"><tr data-start="188" data-end="277"><td><strong data-start="190" data-end="217">Table of Contents (TOC)</strong></td><td>✅❓</td><td>Automatically supported via heading tags in ReadMe</td></tr><tr data-start="278" data-end="350"><td><strong data-start="280" data-end="294">admonition</strong></td><td>❌✅</td><td>Can be mimicked via MDX components</td></tr><tr data-start="351" data-end="421"><td><strong data-start="353" data-end="371">pymdownx.tilde</strong></td><td>✅✅</td><td>Strikethrough and subscript work</td></tr><tr data-start="422" data-end="489"><td><strong data-start="424" data-end="446">pymdownx.highlight</strong></td><td>✅✅</td><td>Code block highlighting works</td></tr><tr data-start="490" data-end="560"><td><strong data-start="492" data-end="517">pymdownx.inlinehilite</strong></td><td>✅✅</td><td>Inline syntax highlighting works</td></tr><tr data-start="561" data-end="659"><td><strong data-start="563" data-end="603">pymdownx.snippets (Reusable Content)</strong></td><td>❌❌</td><td>No programmatic way to import reusable content</td></tr><tr data-start="660" data-end="732"><td><strong data-start="662" data-end="686">pymdownx.superfences</strong></td><td>✅✅</td><td>Nested fenced blocks are supported</td></tr><tr data-start="733" data-end="806"><td><strong data-start="735" data-end="753">pymdownx.emoji</strong></td><td>✅✅</td><td>GitHub-style <code data-start="782" data-end="791">:emoji:</code> syntax works</td></tr><tr data-start="807" data-end="983"><td><strong data-start="809" data-end="828">pymdownx.tabbed</strong></td><td>✅❓</td><td>We have a component for this, but not in their exact syntax (<a data-start="904" data-end="980" rel="noopener" target="_new" href="https://facelessuser.github.io/pymdown-extensions/extensions/tabbed/">Docs</a>)</td></tr><tr data-start="984" data-end="1131"><td><strong data-start="986" data-end="1020">Details (Collapsible Sections)</strong></td><td>❌✅</td><td>Requires a workaround (<a data-start="1051" data-end="1128" rel="noopener" target="_new" href="https://facelessuser.github.io/pymdown-extensions/extensions/details/">Docs</a>)</td></tr><tr data-start="1132" data-end="1206"><td><strong data-start="1134" data-end="1155">pymdownx.tasklist</strong></td><td>✅✅</td><td>Task lists <code data-start="1179" data-end="1184">[ ]</code> <code data-start="1185" data-end="1190">[x]</code> are supported</td></tr><tr data-start="1207" data-end="1365"><td><strong data-start="1209" data-end="1219">smarty</strong></td><td>❌✅</td><td>Needs a replacement or workaround (<a data-start="1277" data-end="1362" rel="noopener" target="_new" href="https://facelessuser.github.io/pymdown-extensions/extensions/smartsymbols/?h=">Docs</a>)</td></tr><tr data-start="1366" data-end="1527"><td><strong data-start="1368" data-end="1386">pymdownx.caret</strong></td><td>❌✅</td><td>Requires a workaround for <code data-start="1428" data-end="1435">&lt;ins&gt;</code> and <code data-start="1440" data-end="1447">&lt;sup&gt;</code> (<a data-start="1449" data-end="1524" rel="noopener" target="_new" href="https://facelessuser.github.io/pymdown-extensions/extensions/caret/">Docs</a>)</td></tr><tr data-start="1528" data-end="1684"><td><strong data-start="1530" data-end="1549">pymdownx.critic</strong></td><td>❌✅</td><td>Requires a workaround for Critic Markup (<a data-start="1605" data-end="1681" rel="noopener" target="_new" href="https://facelessuser.github.io/pymdown-extensions/extensions/critic/">Docs</a>)</td></tr></tbody></table>
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