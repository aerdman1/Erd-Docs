---
title: aersdafas
deprecated: false
hidden: false
metadata:
  robots: index
---
<StepperComponent
  steps={[
    { header: "Step 1", content: <p>Welcome to step 1!</p> },
    { header: "Step 2", content: <p>Now enter your details.</p> },
    { header: "Step 3", content: <p>Review your information.</p> },
    { header: "Step 4", content: <p>Almost done!</p> },
    { header: "Step 5", content: <p>Final confirmation.</p> },
  ]}
/>

<HTMLBlock>{`
<style>
  @keyframes fadeIn {
    0% { opacity: 0; }
    100% { opacity: 1; }
  }

  .content-body .rm-Markdown {
    opacity: 0;
    animation: fadeIn 1.8s ease-in-out forwards;
  }
</style>
`}</HTMLBlock>