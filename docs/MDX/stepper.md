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
</div>

<div>
  <h2>Green Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="green"
    steps={[
      { header: "Step 1", content: <p>Content for step 1.</p>, stepType: "circle" },
      { header: "Step 2", content: <p>Content for step 2.</p>, stepType: "square" },
      { header: "Step 3", content: <p>Content for step 3.</p>, stepType: "circle" },
      { header: "Step 4", content: <p>Content for step 4.</p>, stepType: "square" },
    ]}
  />

  <h2>Green Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="green"
    steps={[
      { header: "Step 1", content: <p>Content for step 1.</p>, stepType: "square" },
      { header: "Step 2", content: <p>Content for step 2.</p>, stepType: "circle" },
      { header: "Step 3", content: <p>Content for step 3.</p>, stepType: "square" },
      { header: "Step 4", content: <p>Content for step 4.</p>, stepType: "circle" },
    ]}
  />

  <h2>Orange Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="orange"
    steps={[
      { header: "Step A", content: <p>Content for step A.</p>, stepType: "circle" },
      { header: "Step B", content: <p>Content for step B.</p>, stepType: "square" },
      { header: "Step C", content: <p>Content for step C.</p>, stepType: "circle" },
      { header: "Step D", content: <p>Content for step D.</p>, stepType: "square" },
    ]}
  />

  <h2>Orange Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="orange"
    steps={[
      { header: "Step A", content: <p>Content for step A.</p>, stepType: "square" },
      { header: "Step B", content: <p>Content for step B.</p>, stepType: "circle" },
      { header: "Step C", content: <p>Content for step C.</p>, stepType: "square" },
      { header: "Step D", content: <p>Content for step D.</p>, stepType: "circle" },
    ]}
  />

  <h2>Yellow Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="yellow"
    steps={[
      { header: "Step 1", content: <p>Content for step 1.</p>, stepType: "circle" },
      { header: "Step 2", content: <p>Content for step 2.</p>, stepType: "square" },
      { header: "Step 3", content: <p>Content for step 3.</p>, stepType: "circle" },
      { header: "Step 4", content: <p>Content for step 4.</p>, stepType: "square" },
    ]}
  />

  <h2>Yellow Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="yellow"
    steps={[
      { header: "Step 1", content: <p>Content for step 1.</p>, stepType: "square" },
      { header: "Step 2", content: <p>Content for step 2.</p>, stepType: "circle" },
      { header: "Step 3", content: <p>Content for step 3.</p>, stepType: "square" },
      { header: "Step 4", content: <p>Content for step 4.</p>, stepType: "circle" },
    ]}
  />

  <h2>Indigo Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="indigo"
    steps={[
      { header: "Step X", content: <p>Content for step X.</p>, stepType: "circle" },
      { header: "Step Y", content: <p>Content for step Y.</p>, stepType: "square" },
      { header: "Step Z", content: <p>Content for step Z.</p>, stepType: "circle" },
      { header: "Step W", content: <p>Content for step W.</p>, stepType: "square" },
    ]}
  />

  <h2>Indigo Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="indigo"
    steps={[
      { header: "Step X", content: <p>Content for step X.</p>, stepType: "square" },
      { header: "Step Y", content: <p>Content for step Y.</p>, stepType: "circle" },
      { header: "Step Z", content: <p>Content for step Z.</p>, stepType: "square" },
      { header: "Step W", content: <p>Content for step W.</p>, stepType: "circle" },
    ]}
  />

  <h2>White Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="white"
    steps={[
      { header: "Step 1", content: <p>Content for step 1.</p>, stepType: "circle" },
      { header: "Step 2", content: <p>Content for step 2.</p>, stepType: "square" },
      { header: "Step 3", content: <p>Content for step 3.</p>, stepType: "circle" },
      { header: "Step 4", content: <p>Content for step 4.</p>, stepType: "square" },
    ]}
  />

  <h2>White Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="white"
    steps={[
      { header: "Step 1", content: <p>Content for step 1.</p>, stepType: "square" },
      { header: "Step 2", content: <p>Content for step 2.</p>, stepType: "circle" },
      { header: "Step 3", content: <p>Content for step 3.</p>, stepType: "square" },
      { header: "Step 4", content: <p>Content for step 4.</p>, stepType: "circle" },
    ]}
  />

  <h2>Black Horizontal (Mixed Step Types)</h2>

  <StepperComponent
    verticalFalse
    backgroundTheme="black"
    steps={[
      { header: "Step Alpha", content: <p>Content for step Alpha.</p>, stepType: "circle" },
      { header: "Step Beta", content: <p>Content for step Beta.</p>, stepType: "square" },
      { header: "Step Gamma", content: <p>Content for step Gamma.</p>, stepType: "circle" },
      { header: "Step Delta", content: <p>Content for step Delta.</p>, stepType: "square" },
    ]}
  />

  <h2>Black Vertical (Mixed Step Types)</h2>

  <StepperComponent
    verticalTrue
    backgroundTheme="black"
    steps={[
      { header: "Step Alpha", content: <p>Content for step Alpha.</p>, stepType: "square" },
      { header: "Step Beta", content: <p>Content for step Beta.</p>, stepType: "circle" },
      { header: "Step Gamma", content: <p>Content for step Gamma.</p>, stepType: "square" },
      { header: "Step Delta", content: <p>Content for step Delta.</p>, stepType: "circle" },
    ]}
  />
</div>

<HTMLBlock>{`
<style>
  .content-body .rm-Markdown {
    opacity: 0;
  }
</style>
`}</HTMLBlock>