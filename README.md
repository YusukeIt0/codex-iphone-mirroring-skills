# iPhone Mirroring skill

Reusable agent instructions for operating iPhone apps through Apple's iPhone Mirroring on a Mac, checking the result, and recovering from ambiguous input.

The skill needs an existing desktop-control tool with macOS app access, screenshots, pointer input and keyboard input. Installing this repository does not supply those capabilities or grant device access.

## Contents

- [`iphone-mirroring`](skills/iphone-mirroring/SKILL.md): shared operating workflow.
- [`even-app-operations`](skills/even-app-operations/SKILL.md): the integrated Even operating skill, including installed/developer/prototype routes, stop/reopen, updates, text entry and physical acceptance.
- Tool and input references are loaded only when relevant.
- [`Validation`](docs/validation.md): observed environments, practical checks and remaining limitations.

## Install and use

Copy both `skills/iphone-mirroring` and `skills/even-app-operations` into the same skill directory supported by your agent. Keep their folder names: relative links connect the shared workflow and the Even procedures. For Codex, a supported user-level location is `~/.agents/skills/iphone-mirroring`; repository-local skills can go in `.agents/skills/`.

For Even tasks, invoke `$even-app-operations`; it loads the shared Mirroring guidance as needed. The integrated Even skill replaces an older installation of the same name when you choose to install this repository.

Example request:

> Use $iphone-mirroring to open the requested iPhone app, perform the agreed task, and verify the result on screen.

The first tested tool environment is Codex with native Computer Use through `cua_repl`. Compatibility with another tool requires adapting its documented calls and testing them. Do not assume a CLI-only installation has desktop control.

## Contribute an observation

Include the OS/app/tool versions, starting screen, exact action, visible result, repeatability, and how the original state was restored. Use synthetic text and omit personal or account information. A useful failure report distinguishes an unchanged screen from a rejected tool call or an inactive mirroring session.

## Sources

- [Apple: iPhone Mirroring](https://support.apple.com/en-us/120421)
- [OpenAI: Skills](https://learn.chatgpt.com/docs/customization/overview#skills)

Not affiliated with Apple or OpenAI. Apple and OpenAI product names identify the environments used.
