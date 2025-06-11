---
title: Callouts
deprecated: false
hidden: false
icon: fad fa-file-lines
metadata:
  robots: index
---
> 📘 TEST

> 🚧 TEST

> 👍 TEST

> ❗️ TEST

> ℹ️ ALT

> ⚠️ TEST

> ✅ TEST

> 🛑 TEST

<HTMLBlock>{`
<style>
/* Testing: random colors for callout themes */

.markdown-body .callout.callout_info {
  /* originally blue/info; now random */
  --text: #3A0CA3;
  --title: #3A0CA3;
  --background: #E0B3FF;
  --border: #7B2CBF;
  color: var(--text);
  background-color: var(--background);
  border: 2px solid var(--border);
}

.markdown-body .callout.callout_okay {
  /* originally green/success; now random */
  --text: #03506F;
  --title: #03506F;
  --background: #B3E5FC;
  --border: #028090;
  color: var(--text);
  background-color: var(--background);
  border: 2px solid var(--border);
}

.markdown-body .callout.callout_warn {
  /* originally orange/warning; now random */
  --text: #FF6B6B;
  --title: #FF6B6B;
  --background: #FFF3B0;
  --border: #F08A5D;
  color: var(--text);
  background-color: var(--background);
  border: 2px solid var(--border);
}

.markdown-body .callout.callout_error {
  /* originally red/error; now random */
  --text: #6A040F;
  --title: #6A040F;
  --background: #FFADAD;
  --border: #D00000;
  color: var(--text);
  background-color: var(--background);
  border: 2px solid var(--border);
}

.markdown-body .callout.callout_default {
  /* fallback theme; now random neutral */
  --text: #1A1A1D;
  --title: #1A1A1D;
  --background: #C5C6C7;
  --border: #4E4E50;
  color: var(--text);
  background-color: var(--background);
  border: 2px solid var(--border);
}


</style>
`}</HTMLBlock>