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
    { header: "Step 1", content: <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 2", content: <p>Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 3", content: <p>Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 4", content: <p>Vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
  ]}
/>

<StepperComponent
  verticalTrue
  steps={[
    { header: "Step 1", content: <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 2", content: <p>Praesent nibh nisl, iaculis in vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "square" },
    
    { header: "Step 3", content: <p>Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "circle" },
    
    { header: "Step 4", content: <p>Vulputate vitae, finibus eu tellus. Nunc vitae nunc pulvinar, imperdiet enim id, ornare massa.
     </p>, stepType: "square" },
    
  ]}
/>

<HTMLBlock>{`
<style>
  .content-body .rm-Markdown {
    opacity: 0;
  }
</style>
`}</HTMLBlock>