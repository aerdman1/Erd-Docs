---
title: Sample Page
deprecated: false
hidden: false
metadata:
  robots: index
---
| Column 1 | Column 2                                                   |
| -------- | ---------------------------------------------------------- |
| Row 1    | <table><tr><td>Nested 1</td><td>Nested 2</td></tr></table> |
| Row 2    | Normal content                                             |

| Outer Header 1 | Outer Header 2                                                                                          |
| -------------- | ------------------------------------------------------------------------------------------------------- |
| Row 1, Col 1   | <table><tr><td>Nested Table 1</td><td>Nested Table 2</td></tr></table>                                  |
| Row 2, Col 1   | Normal Text                                                                                             |
| Row 3, Col 1   | <table><tr><td>Deep Nested</td><td><table><tr><td>Even Deeper</td></tr></table></td></tr></table>       |
| Row 4, Col 1   | <ul><li>Nested List Item 1</li><li>Nested List Item 2</li></ul>                                         |
| Row 5, Col 1   | <table><tr><td>Table Inside</td><td><ul><li>Mixing Lists</li><li>And Tables</li></ul></td></tr></table> |

| Feature         | Description                                                                                                                     | Example Content                                                                                                                                                                                                                                                                           |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Lists in Tables | <ul><li>Supports unordered lists</li><li>Works with nested lists<ul><li>Nested item 1</li><li>Nested item 2</li></ul></li></ul> | <ol><li>Step 1</li><li>Step 2</li></ol> <Glossary>parliament</Glossary>                                                                                                                                                                                                                   |
| Formatting      | **Bold text** **Italic text**                                                                                                   | <code>Inline code</code>                                                                                                                                                                                                                                                                  |
| Block Elements  | <blockquote>This is a blockquote inside a table.</blockquote>                                                                   | <details><summary>Click to expand</summary><p>This is hidden text.</p></details> <Glossary>parliament</Glossary>                                                                                                                                                                          |
| Code Snippets   | <pre><code>console.log("Hello, World!");</code></pre>                                                                           | ![](https://files.readme.io/751b9a6c7accd626bd5d2aa3a5d20172b4bcd35e78564c9c276860f78731bf58-a29c8744b62ec4b51e366e91a012533f9c6e21638db2c425358cec92a7058d7d-CleanShot_2024-11-08_at_20.10.29.gif)<pre><code>curl -X GET [https://api.example.com](https://api.example.com)</code></pre> |

# MDX SPECIFIC

<Accordion title="My Accordion Title" icon="fa-info-circle">
  Lorem ipsum dolor sit amet, **consectetur adipiscing elit.** Ut enim
  ad minim veniam, quis nostrud exercitation ullamco. Excepteur sint
  occaecat cupidatat non proident!
</Accordion>

<Cards columns={4}>
  <Card title="First Card" href="https://readme.com" icon="fa-home" target="_blank">
    Neque porro quisquam est qui dolorem ipsum quia
  </Card>

  <Card title="Second Card" icon="fa-user">
    *Lorem ipsum dolor sit amet, consectetur adipiscing elit*
  </Card>

  <Card title="Third Card" icon="fa-star">
    > Ut enim ad minim veniam, quis nostrud ullamco
  </Card>

  <Card title="Fourth Card" icon="fa-question">
    **Excepteur sint occaecat cupidatat non proident**
  </Card>
</Cards>

<Columns layout="auto">
  <Column>
    Neque porro quisquam est qui dolorem ipsum quia
  </Column>

  <Column>
    *Lorem ipsum dolor sit amet, consectetur adipiscing elit*
  </Column>

  <Column>
    > Ut enim ad minim veniam, quis nostrud ullamco
  </Column>
</Columns>

<Tabs>
  <Tab title="First Tab">
    Welcome to the content that you can only see inside the first Tab.
  </Tab>

  <Tab title="Second Tab">
    Here's content that's only inside the second Tab.
  </Tab>

  <Tab title="Third Tab">
    Here's content that's only inside the third Tab.
  </Tab>
</Tabs>