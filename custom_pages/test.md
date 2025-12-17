---
title: Test123
fullscreen: false
hidden: false
---
```asp Custom
throw 404; // Throw exception with code
throw (404, "Not found"); // Throw with data

assert (condition) throw 404; 
assert (!condition) throw 404;
```

<HTMLBlock>{`
<style>
  /* Entire tabs container */
  .CodeTabs {
    background-color: #2d2d2d !important;
    border-radius: 8px !important;
    overflow: hidden;
  }

  /* Toolbar at top */
  .CodeTabs-toolbar {
    background-color: #1f1f1f !important;
    border-bottom: 1px solid #444 !important;
  }
  .CodeTabs-toolbar button {
    background: transparent !important;
    color: #ccc !important;
    border: none !important;
  }

  /* Inner wrapper and pre/code */
  .CodeTabs-inner,
  .CodeTabs-inner pre,
  .CodeTabs-inner code {
    background-color: transparent !important;
    margin: 0 !important;
    padding: .5rem !important;
    font-family: Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
  }

  /* CodeMirror surface */
  .cm-s-neo {
    background-color: transparent !important;
    color: rgb(178, 204, 214) !important; /* base/punctuation */
  }

  /* Keywords (throw/assert) */
  .cm-s-neo .cm-variable {
    color: rgb(199, 146, 234) !important;
  }

  /* Numbers (404) */
  .cm-s-neo .cm-number {
    color: rgb(247, 140, 108) !important;
  }

  /* Strings */
  .cm-s-neo .cm-string {
    color: rgb(195, 232, 141) !important;
  }

  /* Comments */
  .cm-s-neo .cm-comment {
    color: rgb(105, 112, 152) !important;
    font-style: italic !important;
  }

  /* Operators (the !) */
  .cm-s-neo .cm-operator {
    color: rgb(137, 221, 255) !important;
  }
</style>
`}</HTMLBlock>