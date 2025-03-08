---
title: Stepper
deprecated: false
hidden: false
metadata:
  robots: index
---
<StepperComponent
  verticalTrue
  steps={[
    { header: "Step 1", content: <p>Vertical step 1 content! Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 2", content: <p>Vertical step 1 content! Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "square" },
    
    { header: "Step 3", content: <p>Vertical step 1 content! Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 4", content: <p>Vertical step 1 content! Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
  ]}
/>

<HTMLBlock>{`
<style>
  .content-body .rm-Markdown {
    opacity: 0;
  }
</style>
`}</HTMLBlock>