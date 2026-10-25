# Native Computer Use

Read the current tool documentation first. Use `cua_repl` for UI interaction; do not substitute shell-based event injection or undocumented key codes.

Bind the host with `await cua.getApp('com.apple.ScreenContinuity')`. Keep that handle while valid. Inspect both the host accessibility state and the phone screenshot as needed. The phone's controls may be absent from the host accessibility tree.

Use screenshot coordinates exactly as defined by the current tool. Derive every target from a fresh observation. After an action, obtain the required accessibility state; inspect a screenshot for the phone's actual result. Host AX text remaining unchanged is normal.

Apple documents Command-1 for Home, Command-2 for the app switcher and Command-3 for Spotlight. In this tool their key strings are `super+1`, `super+2`, and `super+3`. Home and app switcher were observed working; Spotlight was inconsistent in the tested session. The visible Home Search control provided an alternative. Prefer an already visible app icon over typing a search unnecessarily.

Observe transitions before issuing dependent actions. Input and display can lag. In particular, a transient language menu can disappear before a click arrives, exposing an unrelated control underneath. Do not queue clicks against transient overlays.

For scrolling, start with one small native `scroll` over the intended region. Compare visible landmarks. Page counts are requests, not measured movement; requesting three pages did not reliably move farther than one in the tested setup.

Native `paste` temporarily sets the Mac clipboard and restores it. This is significant for remote paste; see [text input](text-input.md). A successful return is not a correctness check.

If screenshot capture is unavailable while AX shows an open host menu, close it using an exposed Cancel action and observe again. This restored capture in the tested session. Do not infer device disconnection from that symptom alone.

If the user changes apps or focus during an operation, reobserve before acting. Do not overwrite concurrently entered text.

Source: [Apple iPhone Mirroring guide](https://support.apple.com/en-us/120421). Version-specific shortcuts and capabilities must be checked against the installed OS.
