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

# pymdownx.tilde [https://facelessuser.github.io/pymdown-extensions/extensions/tilde/](https://facelessuser.github.io/pymdown-extensions/extensions/tilde/)

~~Strikethrough~~

text~~subscript~~

***

# pymdownx.highlight

<br />

```python
# This is a test
print("Hello, world!")
```

```python

def hello_world():  
    print("Hello, world!") n

```

```python
If you see **different colors for keywords, comments, and strings**, **syntax highlighting is enabled**.

If everything is the **same color** and only has a gray background, ReadMe does not have syntax highlighting, and you may need a different approach (like a custom MDX component for code blocks).

INLINE: markdown_extensions:
  - pymdownx.highlight
  - pymdownx.inlinehilite
```

<br />

***

:+1:

***

<br />

\--8\<-- "libs/util/README.md"

<br />

> ```
> ```
>
> <br />
>
> :thumbsup: :smile:
>
> <br />
>
> \=== "Python"\`\`\`python\
> print("hello")
>
> ````
>
> <br />
>
> \=== "Java"```java
> System.out.println("hello");
> ````
>
> <br />
>
> ??? example\
> Hidden content inside collapsible block.
>
> <br />
>
> * [x] Task completed
>   * [ ] Task not completed
>
> <br />
>
> (tm) (c) (R)
>
> <br />
>
> This is a reference \[^1]
>
> <br />
>
> [^1]: This is a footnote.
>
> <br />
>
> ^^Insert me^^
>
> <br />
>
> Text^superscript
>
> <br />
>
> \{++ added content ++}
>
> <br />
>
> \{-- removed content --}\
> \`\`\`