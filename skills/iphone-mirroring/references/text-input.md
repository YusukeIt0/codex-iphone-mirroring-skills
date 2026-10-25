# Text input through Mirroring

Prefer copying a complete, committed string on the Mac, pasting it into the iPhone field, and checking the rendered result. Japanese input-source switching and rapid simulated typing were unreliable in the tested environment.

## Persistent clipboard procedure

1. Inspect the destination. Preserve existing user text. For experiments, use synthetic text in a search field or an authorized unsent draft. Never use Return in a composer merely to confirm input.
2. Use a known local scratch document in a writable, non-synced location. Do not create an untitled cloud-synced document accidentally. Through the supported desktop UI, place the exact intended string in the scratch document and verify it there.
3. Select the intended string and use ordinary Command-C. This leaves it on the Mac clipboard. It replaces the clipboard; do not claim the old contents were preserved.
4. Focus the iPhone destination and verify the caret. Let the screen transition finish. Use ordinary Command-V (`pressKey('super+v')` in native CUA).
5. Wait for any Continuity paste indicator to finish, then inspect the full visible string, including punctuation, script and line breaks. Do not send or submit until it matches.
6. If the exact text does not appear after focus and any paste indicator settle, stop automated input and ask the user to enter only the required string in the already-open field. Do not ask them to send it. Inspect their completed input, then resume the remaining authorized work. Do not cycle through alternate key combinations, paste wrappers or repeated retries. Clear only synthetic text from the failed attempt; preserve user content.
7. Clear synthetic drafts and remove or retain the scratch artifact according to the user's task. Report any remaining artifact or clipboard change.

Two mixed-script strings pasted correctly into Settings search using this procedure. This is bounded evidence, not a guarantee for every app. A Spotlight attempt showed a paste indicator without confirmed text afterward. See the repository validation record for app-specific checks.

## Why not the one-call paste wrapper?

In the tested native CUA environment, `app.paste(newText)` in a mirrored field inserted a previous clipboard value. The tool documentation says this wrapper restores the old Mac clipboard. A timing interaction with Continuity is a hypothesis, not a verified internal cause. Ordinary copying followed by Command-V avoids deliberately restoring the clipboard before the phone has finished reading it.

## Input sources and direct typing

The mirrored iPhone input source may differ from the Mac source. Do not infer it from the Mac menu bar or a successful key call. Rapid `typeText` produced missing or transliterated characters. Individually paced roman keys produced Japanese composition successfully in one Settings test, but this did not establish reliable mixed-script entry.

The user demonstrated holding the MacBook fn/globe key; a visible menu offered English and Japanese input. The tool's `pressKey('fn')` was rejected as an unknown key, so autonomous fn switching was not established. Clicking the transient menu was unreliable and appeared to reach an underlying Settings row after a delay. Do not prescribe this as a verified automated switch.

Control-Space, Caps Lock and JIS key-name attempts did not establish a reliable switch in this environment. Do not change keyboard remapping software, system programs or app binaries to work around this limitation. For normal work, request the required text from the user instead of troubleshooting input-source switching. Investigate keyboard switching only when explicitly requested.

Background reference: [Junichi Ito's fn/globe-key article](https://blog.jnito.com/entry/2024/11/12/091057). Its keyboard-remapping configuration is not part of this procedure.
