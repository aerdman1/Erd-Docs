---
title: Test
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
  /* Charcoal-black background */
  .cm-s-neo {
    background-color: #2d2d2d !important;
    color: rgb(178, 204, 214) !important; /* fallback/base text color */
  }

  /* Keywords & “throw”/“assert” */
  .cm-s-neo .cm-variable {
    color: rgb(199, 146, 234) !important;
  }

  /* Numbers like 404 */
  .cm-s-neo .cm-number {
    color: rgb(247, 140, 108) !important;
  }

  /* Strings */
  .cm-s-neo .cm-string {
    color: rgb(195, 232, 141) !important;
  }

  /* Comments (italic) */
  .cm-s-neo .cm-comment {
    color: rgb(105, 112, 152) !important;
    font-style: italic !important;
  }

  /* Operators like ! */
  .cm-s-neo .cm-operator {
    color: rgb(137, 221, 255) !important;
  }
</style>
`}</HTMLBlock>