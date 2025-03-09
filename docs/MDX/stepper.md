---
title: Stepper
deprecated: false
hidden: false
metadata:
  robots: index
---
<div>
  <h2>Purple Horizontal (All Circles)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="purple"
    steps={[
      { header: "Plan Your Documentation", content: <p>Define the purpose of your documentation and identify your target audience. Outline key topics and gather relevant resources before writing.</p>, stepType: "circle" },
      { header: "Write Effective Content", content: <p>Use simple language, structured explanations, and break complex concepts into digestible sections.</p>, stepType: "circle" },
      { header: "Format Content Effectively", content: <p>Utilize headings, bullet points, and tables to improve readability. Add images, code snippets, and examples to enhance clarity.</p>, stepType: "circle" },
      { header: "Use Interactive Elements", content: <p>Incorporate API explorers, live code examples, and try-it-yourself features for better engagement and hands-on learning.</p>, stepType: "circle" },
      { header: "Publish and Maintain Content", content: <p>Test documentation for accuracy and clarity before publishing. Keep it updated to reflect new features, changes, or improvements.</p>, stepType: "circle" },
    ]}
  />

  <h2>Purple Vertical (All Circles)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="purple"
    steps={[
      { header: "Plan Your Documentation", content: <p>Define the purpose of your documentation and identify your target audience. Outline key topics and gather relevant resources before writing.</p>, stepType: "circle" },
      { header: "Write Effective Content", content: <p>Use simple language, structured explanations, and break complex concepts into digestible sections.</p>, stepType: "circle" },
      { header: "Format Content Effectively", content: <p>Utilize headings, bullet points, and tables to improve readability. Add images, code snippets, and examples to enhance clarity.</p>, stepType: "circle" },
      { header: "Use Interactive Elements", content: <p>Incorporate API explorers, live code examples, and try-it-yourself features for better engagement and hands-on learning.</p>, stepType: "circle" },
      { header: "Publish and Maintain Content", content: <p>Test documentation for accuracy and clarity before publishing. Keep it updated to reflect new features, changes, or improvements.</p>, stepType: "circle" },
    ]}
  />

  <h2>Blue Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="blue"
    steps={[
      { header: "Plan Your Documentation", content: <p>Define the purpose of your documentation and identify your target audience. Outline key topics and gather relevant resources before writing.</p>, stepType: "square" },
      { header: "Write Effective Content", content: <p>Use simple language, structured explanations, and break complex concepts into digestible sections.</p>, stepType: "square" },
      { header: "Format Content Effectively", content: <p>Utilize headings, bullet points, and tables to improve readability. Add images, code snippets, and examples to enhance clarity.</p>, stepType: "square" },
      { header: "Use Interactive Elements", content: <p>Incorporate API explorers, live code examples, and try-it-yourself features for better engagement and hands-on learning.</p>, stepType: "square" },
      { header: "Publish and Maintain Content", content: <p>Test documentation for accuracy and clarity before publishing. Keep it updated to reflect new features, changes, or improvements.</p>, stepType: "square" },
    ]}
  />

  <h2>Blue Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="blue"
    steps={[
      { header: "Plan Your Documentation", content: <p>Define the purpose of your documentation and identify your target audience. Outline key topics and gather relevant resources before writing.</p>, stepType: "square" },
      { header: "Write Effective Content", content: <p>Use simple language, structured explanations, and break complex concepts into digestible sections.</p>, stepType: "square" },
      { header: "Format Content Effectively", content: <p>Utilize headings, bullet points, and tables to improve readability. Add images, code snippets, and examples to enhance clarity.</p>, stepType: "square" },
      { header: "Use Interactive Elements", content: <p>Incorporate API explorers, live code examples, and try-it-yourself features for better engagement and hands-on learning.</p>, stepType: "square" },
      { header: "Publish and Maintain Content", content: <p>Test documentation for accuracy and clarity before publishing. Keep it updated to reflect new features, changes, or improvements.</p>, stepType: "square" },
    ]}
  />

  <h2>Red Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="red"
    steps={[
      { header: "Step A", content: <p>Content for step A.</p>, stepType: "circle" },
      { header: "Step B", content: <p>Content for step B.</p>, stepType: "square" },
      { header: "Step C", content: <p>Content for step C.</p>, stepType: "circle" },
      { header: "Step D", content: <p>Content for step D.</p>, stepType: "square" },
    ]}
  />

  <h2>Red Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="red"
    steps={[
      { header: "Step A", content: <p>Content for step A.</p>, stepType: "square" },
      { header: "Step B", content: <p>Content for step B.</p>, stepType: "circle" },
      { header: "Step C", content: <p>Content for step C.</p>, stepType: "square" },
      { header: "Step D", content: <p>Content for step D.</p>, stepType: "circle" },
    ]}
  />

  {/* Add additional examples for green, orange, yellow, indigo, white, black as needed */}
</div>

<HTMLBlock>{`
<style>
  .content-body .rm-Markdown {
    opacity: 0;
  }
</style>
`}</HTMLBlock>