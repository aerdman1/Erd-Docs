---
title: AI & MCP
excerpt: Ask questions about Orbit in plain English, or plug these docs into your AI tools.
deprecated: false
hidden: false
icon: fad fa-sparkles
metadata:
  robots: index
---
This hub is built to be read by people **and** by AI. Nothing on this page needed custom code: it’s all part of ReadMe.

## Ask AI

Click **Ask AI** in the header and ask something like *“How do I book a CubeSat to sun-synchronous orbit?”* The answer is drawn from these guides and the API Reference, with links back to the pages it used.

## Connect your AI tools with MCP

Every ReadMe hub can run an **MCP server**. Connect it to Claude, Cursor or another MCP client, and the client can search these docs and read the Orbit API definition while it writes your integration.

<MCPIntro url="https://erdman.readme.io/mcp" />

Alongside the standard tools, this server has a **custom tool**, `plan-orbit-booking`. It hands an agent the booking steps in order, and it was written in the dashboard with no code.

## Docs for LLMs

| What                     | Where                                                           |
| :----------------------- | :-------------------------------------------------------------- |
| An index of every page   | [`/llms.txt`](https://erdman.readme.io/llms.txt)                |
| Any page as Markdown     | Add `.md` to the page URL, like `/docs/quickstart.md`           |
| The Orbit API definition | Shown with each endpoint in the [API Reference](/reference/listlaunches) |

<Callout icon="✨" theme="info">
  Try it: paste `https://erdman.readme.io/docs/quickstart.md` into your AI tool and ask it to write a booking script in your language.
</Callout>

<Accordion title="How this page is built" icon="fa-wand-magic-sparkles">
  * `MCPIntro`, a **built-in ReadMe component** that shows this hub’s MCP server and how to connect to it
  * A **custom MCP tool**, added in the dashboard
  * **Ask AI**, `llms.txt` and the `.md` page export are hub features, turned on in settings
  * A **table** and an **info** Callout
</Accordion>
