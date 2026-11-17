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

Pick your client:

<Tabs>
  <Tab title="Claude Code" icon="fa-terminal">
    ```shell
    claude mcp add --transport http orbit https://erdman.readme.io/mcp
    ```
  </Tab>

  <Tab title="Cursor" icon="fa-arrow-pointer">
    ```json ~/.cursor/mcp.json
    {
      "mcpServers": {
        "orbit": { "url": "https://erdman.readme.io/mcp" }
      }
    }
    ```
  </Tab>

  <Tab title="VS Code" icon="fa-code">
    ```json .vscode/mcp.json
    {
      "servers": {
        "orbit": { "type": "http", "url": "https://erdman.readme.io/mcp" }
      }
    }
    ```
  </Tab>
</Tabs>

The **Copy Page** menu at the top of every page has the same options, one click each.

### What the server can do

| Tool                 | What it does                                                              |
| :------------------- | :------------------------------------------------------------------------ |
| `search`, `fetch`    | Search these guides and read any page                                     |
| `list-endpoints`     | List every Orbit endpoint                                                 |
| `search-endpoints`   | Find endpoints by keyword, parameter or field                             |
| `get-endpoint`       | Read one endpoint’s parameters, schemas and auth                          |
| `execute-request`    | Call the API for real, with the user’s key                                |
| `plan-orbit-booking` | A **custom tool**: the booking steps in order, written in the dashboard with no code |

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
  * **Tabs** with a code block per MCP client
  * The hub’s **MCP server**, turned on in settings, plus a **custom MCP tool** added in the dashboard
  * **Ask AI**, `llms.txt` and the `.md` page export are hub features, turned on in settings
  * A **table** and an **info** Callout
</Accordion>
