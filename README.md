# Codex skills for iPhone Mirroring & Even Hub

Skills for **OpenAI Codex** to control iPhone apps and Even Hub from a Mac through Apple’s iPhone Mirroring.

**Target environment: Codex with native Computer Use (`cua_repl`). Claude, Claude Code and other agents are not supported or tested by this project; these instructions are not a drop-in setup for them.**

## How it works

1. **Mirror your iPhone on your Mac** using Apple’s iPhone Mirroring app.
2. **Give Codex a task.** Its desktop-control tool clicks, scrolls and types in the mirrored window.
3. **The skill guides the agent** through known routes, checks the visible result and handles failed input.

## Included skills

| Skill | Use it for |
| --- | --- |
| [iphone-mirroring](skills/iphone-mirroring/SKILL.md) | General navigation, scrolling, text entry and screen verification |
| [even-app-operations](skills/even-app-operations/SKILL.md) | Even Hub browsing, plugin management, developer builds, update checks, stop/reopen and device verification |

The Even skill is self-contained and can be installed on its own. It includes the procedures used in the maintainer’s local workflow.

## Requirements

- A Mac and iPhone with [Apple’s iPhone Mirroring](https://support.apple.com/en-us/120421) working.
- Codex with native Computer Use (`cua_repl`) available for Mac apps. A CLI-only setup without desktop control is not sufficient.
- For Even tasks: the Even iPhone app and access to the relevant plugin/build.

**Tested tool:** Codex native Computer Use (`cua_repl`). These files provide instructions; they do not install a control tool or grant device access.

## Install

Download or clone this repository, then copy the desired folder from `skills/` into your Codex skill directory.

| Scope | Codex location |
| --- | --- |
| Your user account | `~/.agents/skills/` |
| One repository | `.agents/skills/` |

Update an existing skill of the same name instead of keeping duplicate installations. See [Codex skill setup](https://learn.chatgpt.com/docs/build-skills#where-codex-loads-local-skills).

## Example tasks

> Use $iphone-mirroring to open the requested iPhone app and inspect its screen.

> Use $even-app-operations to check whether my uploaded developer plugin has an update. Do not install it yet.

## Input fallback

**Copy and paste → verify the text → ask for manual entry if needed → resume.**

If manual entry also fails, use a route that needs no text or report the step as unverified. Sending and submitting remain separate actions.

## Known limits

| Area | Current status |
| --- | --- |
| Even navigation, ranking tabs and category sorting | Observed working |
| Plugin removal | Observed working with explicit authorization |
| Developer update refresh | User-confirmed route; no pending update was installed during validation |
| Cross-device paste and search input | Unreliable in the tested environment |
| Some detail-page scrolling and image gestures | Not established |

See [validation evidence](docs/validation.md) for dates, versions and remaining gaps.

## License

[MIT](LICENSE) — reuse, modify and redistribute with the license notice.

## Improve the skills

Record the starting screen, versions, action, visible result and cleanup. Keep confirmed behavior separate from assumptions. Include no private screenshots, account details or conversations.

Not affiliated with Apple, OpenAI or Even Realities.
