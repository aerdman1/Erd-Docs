---
title: Stepper
deprecated: false
hidden: false
metadata:
  robots: index
---
<StepperComponent
  verticalFalse
  steps={[
    { header: "Plan Your Documentation", content: <p>Define the purpose of your documentation and identify your target audience. Outline key topics and gather relevant resources before writing.</p>, stepType: "circle" },
    
    { header: "Write Clear Content", content: <p>Use simple language, structured explanations, and break complex concepts into digestible sections. Follow a consistent tone and style guide.</p>, stepType: "circle" },
    
    { header: "Format Content  Effectively", content: <p>Utilize headings, bullet points, and tables to improve readability. Add images, code snippets, and examples to enhance clarity.</p>, stepType: "circle" },
    
    { header: "Use Interactive Elements", content: <p>Incorporate API explorers, live code examples, and try-it-yourself features for better engagement and hands-on learning.</p>, stepType: "circle" },
    
    { header: "Publish and Maintain", content: <p>Test documentation for accuracy and clarity before publishing. Keep it updated to reflect new features, changes, or improvements.</p>, stepType: "circle" },
  ]}
/>

<HTMLBlock>{`
<style>
  .content-body .rm-Markdown {
    opacity: 0;
  }
</style>
`}</HTMLBlock>