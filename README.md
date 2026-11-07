<p align="center">
  <img src="./assets/hero.svg" width="100%" alt="Prompts"/>
</p>

<p align="center">My personal collection of prompts for Claude Code.</p>

<img src="./assets/h-prompts.svg" width="100%" alt="Prompts"/>

| Prompt | What it does |
|:--|:--|
| [**REA prompt**](prompts/rea-prompt.md) | Analyses an installed app (reverse engineering) and rebuilds it for private use with React + TypeScript |

<p align="center">
  <img src="./assets/rea-flow.svg" width="100%" alt="Installed app → REA report → Rebuild"/>
</p>

<img src="./assets/h-need.svg" width="100%" alt="What you need for the REA prompt"/>

<table>
<tr>
<td width="50%" valign="top">

**🖥️ On the PC**

- Windows PC with the target app **installed** (the prompt searches the installation folder, Start menu and registry; if it is missing, Claude asks whether to install it)
- [Node.js](https://nodejs.org) (LTS) and npm, to run the Vite + React + TypeScript project
- Git (optional, for versioning the result)

</td>
<td width="50%" valign="top">

**✻ In Claude Code**

- [Claude Code](https://claude.com/claude-code) (desktop app or CLI)
- The **`rea` skill**, placed in `C:\Users\<you>\.claude\skills\rea\` (needs `SKILL.md`, plus its `references/` folder). The prompt calls this skill in step 2, without it step 2 fails.
- Reverse-engineering tools for the `rea` skill. If something is missing, the skill points to its `references/toolchain-setup.md`.
- A browser tool for step 5 (testing every feature): the built-in browser pane of the Claude desktop app, or the Playwright plugin
- Optional: the `agent-skills` plugin for coding skills (specs, tests, code review)

</td>
</tr>
</table>

<img src="./assets/h-use.svg" width="100%" alt="How to use"/>

<p align="center">
  <img src="./assets/steps.svg" width="100%" alt="Open, copy, send, approve"/>
</p>

1. Open Claude Code in an empty project folder.
2. Copy the prompt from [prompts/rea-prompt.md](prompts/rea-prompt.md) and replace `[APP-NAME]`.
3. Send it. Claude finds the app, writes the REA report, then builds the rebuild feature by feature.
4. Approve downloads and installs when Claude announces them.

<img src="./assets/h-result.svg" width="100%" alt="Result you get"/>

- 📄 The REA report (`rea-<app-name>-fertig.md`)
- 📊 A table: feature in the original ↔ in the rebuild (present / partial / missing)
- 🚀 A runnable project with the start command (usually `npm install` then `npm run dev`)
- 📝 A short list of what is still missing

<img src="./assets/h-rules.svg" width="100%" alt="Rules built into the prompt"/>

<p align="center">
  <img src="./assets/rules.svg" width="100%" alt="Rules"/>
</p>

- Own code only: no original code, logos, icons, fonts or brand names, and the rebuild gets its own name
- No real accounts or logins of the app are touched
- For private use only, do not publish the rebuild

<p align="center">
  <a href="https://github.com/ShadowSatoshiii"><img src="./assets/footer.svg" width="100%" alt="Made by ShadowSatoshiii"/></a>
</p>
