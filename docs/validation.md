# Validation record

## Scope and environment

Observed on 2026-10-25 using macOS 26.2 (25C56), iPhone Mirroring 1.5 and Codex native Computer Use through `cua_repl`. The iOS version was not independently recorded. Earlier Even navigation observations used Even 2.3.2; the current installed Even version was not rechecked. Dot Link displayed 0.3.36 through the uploaded developer-app route, without a Beta marker. Route alone does not determine build identity.

Tests used synthetic text and reversible navigation. No test message was sent. No keyboard remapping, app binary, system program, permission or installed package was changed. Private screenshots are not included in this repository.

## Results

| Check | Result | Evidence and limit |
| --- | --- | --- |
| Inspect mirrored content | Passed | Screenshots exposed phone content while the host AX tree stayed unchanged |
| Home and app switcher | Passed | Command-1 and Command-2 changed the visible phone screen |
| Spotlight shortcut | Unreliable | Command-3 did not consistently show the expected state; visible Home Search worked |
| Settings scroll | Passed | Stable row landmarks moved after native scroll; requested page count did not reliably scale distance |
| Even page scroll | Passed | Three sequential scrolls moved from the header through transcript content to the composer |
| Rapid direct typing | Failed | Mixed Japanese composition, missing letters and incomplete strings |
| Paced roman keys | Bounded success | Six separately observed keys produced Japanese composition in Settings; not a general input-source solution |
| Native one-call paste | Failed | A previous clipboard value appeared instead of the supplied text |
| Persistent Mac copy, then Command-V | Passed in Settings | Two exact strings: `Mirror4827 日本語テスト` and `日本語ABC4828` |
| Persistent paste in Spotlight | Unverified | A Continuity paste indicator appeared, but the expected final string was not confirmed |
| fn/globe menu | User-assisted observation | Holding the physical key displayed English (Japan) and Japanese kana choices |
| Automated fn switch | Unsupported/unverified | `fn` was rejected by the tool; clicking the transient menu did not verify a switch and appeared to reach a row below it |
| Open Even uploaded app | Passed | Developer hub lower app row opened Dot Link 0.3.36 |
| Even composer copy/paste | Not established | Composer focus frame eventually appeared, but two Command-V attempts did not show the copied string. Subsequent screenshot capture became unavailable while the host Edit menu was active; cancelling that menu restored capture |

## Interpretation

The agreed operating policy is one properly focused copy/paste attempt, visible verification, then a narrow user handoff for text entry if it fails. Resume autonomous work after verifying the user-entered text. Use persistent copy/paste as the preferred input method, with exact visible verification. Success in Settings does not prove success in an Even embedded field. The clipboard wrapper's restoration timing is a possible explanation for stale text, not a confirmed implementation defect. The cause of the Even paste failure remains unknown.

Allow delayed focus and navigation to settle. A click against a short-lived menu may arrive after it closes. Do not infer a successful language switch from the menu disappearing. Do not keep issuing input when screenshots are unavailable.

## Cleanup and final state

The synthetic Mac scratch document was moved from TextEdit iCloud storage into the ignored local `.runtime/` folder and closed. The Mac clipboard was changed during copying and was not restored. At the final phone inspection, the composer contained text different from the synthetic test string. Its origin was not established; it was preserved and not sent. Dot Link remained open.

## Earlier Even route evidence

The integrated `even-app-operations` skill also carries forward observations from 2026-10-24: formal installed-app Home route, My plugins to Developer hub, lower uploaded-app row versus QR prototype route, and top-left stop confirmation returning to the originating list. Developer update refresh by leaving and re-entering the hub was user-confirmed, not an update executed during this test. These observations are dated guidance and must be checked against live labels.

## Revalidation

On another environment, record OS/app/tool versions, starting route, exact action, visible final state, repeatability and cleanup. Test neutral search input before a message draft. Never send just to prove that input worked. Keep failures in the record and avoid promoting a one-device result to a universal guarantee.

## Integration review — 2026-10-25

The existing Even operations skill was integrated as a second skill in this repository. Installed-app, developer-hub, prototype, stop/reopen, update, input and acceptance sections were checked against the source. Historical version examples remain dated; newer observations qualify shortcuts, delayed clicks and build identity. The shared input policy replaces repeated keyboard troubleshooting with a narrow user handoff. Dot Link distribution requirements remain explicitly project-specific. No new device update, message send or release action was performed for this documentation integration.

## Even Hub inspection — 2026-10-25

Scope expanded from a single plugin's routes to the in-app storefront and management surfaces. The running plugin was stopped to inspect the Hub.

| Check | Result | Boundary |
| --- | --- | --- |
| Storefront and discovery | Passed | Featured area, search entry, categories and ranking entry points observed |
| AI category | Passed | Featured area and plugin list loaded |
| Category sorting | Passed | Latest changed the list after loading; Automatic was selected again afterward |
| Popular/New ranking | Passed | Switching tabs displayed distinct lists |
| My plugins sort menu | Inspected | Updates available, Size and Name; reordering not exercised with one remaining item |
| Store details | Passed for opening | Developer, category, rank, images, overview and Get/Open visible |
| Store detail ellipsis | Inspected | Live translation and Share; neither executed |
| Detail scrolling/gallery | Not established | Two vertical scrolls, one horizontal drag and an image tap showed no confirmed change |
| Uninstall | Passed | Explicitly designated OcuClaw was uninstalled after confirmation of irreversible related-data loss; store changed to Get; My plugins required exit/reentry before its row disappeared |
| Search paste | Failed | Prepared Mac query differed from pasted old clipboard text even after an iOS paste prompt; field cleared; user-assisted entry also failed by user report. Search results for the intended query remain unverified |

No other plugin was installed, removed or updated; no message, share or reaction was sent. No personal account details or screenshots are included in this record.

After the Hub inspection, the original uploaded-developer route was reopened. Dot Link 0.3.36, Even Hub connected status and the pre-existing transcript were visibly restored. Search was left empty before exiting.

## Active-skill synchronization — 2026-10-25

The repository Even skill now matches the extended active local `even-app-operations/SKILL.md` byte for byte. It contains its own navigation, Hub management, input fallback and limitations, with no dependency on the generic skill. The earlier separate Hub reference was consolidated into this file. The generic Mirroring skill remains available separately. Future improvements can be tested in the active skill and copied back here; synchronization is manual, not automatic.
