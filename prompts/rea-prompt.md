# REA prompt

Replace `[APP-NAME]` with the app you want to rebuild, then paste everything inside the block into Claude Code.

````markdown
Build the app [APP-NAME] for my private use.

## Build the app [APP-NAME] for my private use.

1. Find the app on my PC (installation folder, Start menu, registry). If it is not installed, tell me briefly and ask whether I should install it.
2. Use the skill `rea` to run a reverse-engineering analysis and save it as `rea-<app-name>-done.md`.
3. Work out for yourself which features the app has and sort them by priority: the most important first, then the rest.
4. Rebuild the app with React (Vite + TypeScript, data stored locally). First a runnable base version, then feature by feature.
5. Test every feature in the browser before you build the next one.

## Rules

- Look, controls and features as close to the original as possible.
- Your own code. Do not copy any original code, logos, icons, fonts or brand names. Give the rebuild its own name.
- Do not touch any real accounts or logins of the app.
- Announce downloads and installations beforehand, briefly.
- Only ask when you really cannot continue.

## At the end I want

- the REA report,
- a table: feature in the original ↔ in the rebuild (present / partial / missing),
- the runnable project with the command to start it,
- a short list of what is still missing.
````

> Note: the original (German) prompt asks for the report as `rea-<app-name>-fertig.md`. The `rea` skill itself writes that German file name. If your skill is unchanged, expect `-fertig.md` instead of `-done.md`.
