---
title: Terminal
excerpt: A CLI session that types itself out.
deprecated: false
hidden: false
icon: fad fa-terminal
metadata:
  robots: index
---
Show a command-line session that plays when it scrolls into view. **Copy** grabs only the commands, and **↻** plays it again.

<Terminal title="orbit — zsh" script="$ npm install -g @erdman/orbit-cli\nadded 1 package in 2s\n$ orbit login\n✔ Logged in as dana@pixelowl.space\n$ orbit launches list --min-capacity 4\n→ lch_9Kd4Mw  Polaris Run  kestrel  SSO  120 kg free\n$ orbit book lch_9Kd4Mw --payload ./pixel-owl.json\n✔ Booked bkg_4Fh8Qp (pending manifest review)" />

The Orbit CLI is made up, like the rest of Orbit.

## Use it

Separate lines with `\n`. Lines that start with `$ ` are commands. Output lines that start with ✔, ✖, ⚠, → or # get their own color.

```mdx
<Terminal title="orbit — zsh" script="$ orbit login\n✔ Logged in\n$ orbit launches list" />
```

| Prop | Values | What it does |
| :--- | :--- | :--- |
| `script` | Text | The session, one line per `\n` |
| `title` | Text | The window title |
| `speed` | Milliseconds | Typing delay per character. Defaults to 28. |
| `animate` | `false` | Show everything at once |

<Accordion title="How it works" icon="fa-wand-magic-sparkles">
  * It waits until it scrolls into view, then types.
  * For readers who turn on reduced motion, the whole session shows at once.
</Accordion>
