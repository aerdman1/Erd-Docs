---
title: Banner Fun
deprecated: false
hidden: false
metadata:
  robots: index
---
\<!--
Banner Component Options

\<Banner&#x20;
&#x20; message="This is my custom banner message!"
&#x20; critical=\{true}        // Preset: Critical alert (overrides all colors if set)
&#x20; warning=\{true}         // Preset: Warning alert
&#x20; standard=\{true}        // Preset: Standard info alert
&#x20; custom=\{true}          // Use custom styles (default if no preset is selected)

&#x20; bannerColor="#ff00ff"  // Background color (only applies for custom banners)
&#x20; bannerTextColor="#ffffff" // Text color (only applies for custom banners)

&#x20; fontSize="18px"        // Optional font size
&#x20; fontWeight="bold"      // Optional font weight
/>

Presets (critical, warning, standard) have built-in colors and styles.
If you set \`custom=\{true}\`, you can fully control the colors and styles.
If no preset is set, the component defaults to "custom".
\-->

\<Banner&#x20;
&#x20; message="This is my banner you can change it or use custom presets!"&#x20;
&#x20; bannerColor="#ff00ff"&#x20;
&#x20; bannerTextColor="#fff"&#x20;
/>