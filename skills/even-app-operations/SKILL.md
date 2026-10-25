---
name: even-app-operations
description: Operate the Even iPhone app and its Even Hub through macOS iPhone Mirroring, including installed apps, uploaded developer builds, prototypes, stopping, updating and physical acceptance. Use for mirrored Even tasks, not the separate Developer Hub website.
---

# Even app operations

Integrated from the existing Even operations skill, with observations from 2026-10-24 and input-policy corrections from 2026-10-25. Read [the shared iPhone Mirroring skill](../iphone-mirroring/SKILL.md) for tool setup, navigation timing and recovery. Install both skill folders together. If already read in the current session, continue applying the procedures rather than rediscovering the routes.

Use cua_repl for UI interaction. Treat the following as observations from 2026-10-24, and refresh the screenshot before choosing controls.

For storefront browsing, search/category navigation, My plugins and uninstall, read [Even Hub management](references/even-hub.md).

## Open the installed app

- Bind iPhone Mirroring with `cua.getApp('com.apple.ScreenContinuity')`. Its AX tree may expose only the Mac window and menus. Use current screenshots for the phone's controls; do not expect app-internal AX elements.
- `super+1` opens iPhone Home and `super+2` the app switcher. The documented `super+3` Spotlight shortcut was inconsistent on 2026-10-25; use visible Home Search or an already visible app icon when needed. Inspect focus before rebinding a stale app handle.
- In Even, the bottom-left house tab opens the home with installed app cards. Open the Dot Link card's icon. The four-square Even Hub tab is a storefront, not the installed-app starting point.
- The observed Dot Link 0.3.25 was a formal release. Do not route through Developer mode or infer Beta merely because this is a test session. Read the actual app version and the user's selected route.
- An Update badge does not need to be pressed to open the installed version. Updating changes the test subject and is a separate decision.
- Coordinates follow the returned screenshot's coordinate system. Do not halve them or reuse remembered coordinates. A safe navigation double-click worked in an earlier observation, but later tests showed delayed navigation. First let a single click settle and inspect the resulting screen; never generalize double-clicking to send, update, or destructive controls.
- To stop the running Even app, tap the top-left diagonal-arrow control in the Dot Link host. The sheet says 「終了しますか？」 and explains that the current function will stop. Choose 「終了」, then verify the originating list returns (home for the formal app, developer hub for the developer app). This was executed successfully. Reopen from the Dot Link card and verify connection/history restoration.
- The host top-right ellipsis exposed an uninstall action, not stop/reload. Do not uninstall to restart.

## Developer hub and prototype mode

Verified in the Even iPhone app 2.3.2 on 2026-10-24:

1. Open the bottom Even Hub tab (four-square icon).
2. Tap the top-right avatar to open 「マイプラグイン」 (My plugins).
3. Tap the top profile/name row or its right chevron. This opens 「開発者ハブ」 (Developer hub). The resulting screen verified the developer destination. Do not assume account editing from the row's appearance.
4. For the uploaded developer app, use the LOWER 「開発中 → Dot Link → 開く」 row. This opened 0.3.24 Beta, while the formal route opened 0.3.25. The user confirmed this is the intended developer-mode app. Do not substitute the upper QR/prototype route. Verify the version each time; these numbers are observations, not permanent targets. On 2026-10-25 the same uploaded-app route opened 0.3.36 without a Beta marker. The route alone does not establish Beta or public-release status. The developer app stops through the same top-left diagonal arrow → 「終了」 confirmation and returns to Developer hub. Its top-right ellipsis showed uninstall, not update.
5. Prototype mode opens 「QRコードをスキャン」. The bottom 「QRコードをスキャンできない場合」 link opens a URL field and 「開始」 button. Only use an intended, authorized development URL. Opening these screens does not require starting a prototype or replacing the installed release.

## Updates

- Formal-app management: Even Hub → top-right avatar → My plugins. Tapping the app name opens the store detail; tapping 「開く」 launches it. In the observed current state, both My plugins and the detail page showed Open for formal 0.3.25, not Update.
- [Even official support](https://support.evenrealities.com/hc/en-us/articles/15688149217167-Even-Hub) says My plugins displays Update when a new release is available. This is documented guidance, not an update executed in this session. The page's Public/Beta tab layout differs from the observed app 2.3.2, so prefer live labels over copied screenshots.
- Developer-app update (user-confirmed 2026-10-24): after a new build is available, go BACK out of Developer hub, then re-enter it. The 「開発中 → Dot Link」 row shows Update after the screen refreshes. Staying on the same screen often does not reflect the new version. Use that Update control, then reopen and verify the target version. Do not confuse this with the upper QR/prototype route or uninstall. In this observation no update was pending (Open, 0.3.24 Beta), so no package update was executed.
- Preserve the selected test version while inspecting procedures. After any authorized update, reopen and read the version/Beta label before treating it as the intended build.

## Japanese and English text input

Use [the shared text-input procedure](../iphone-mirroring/references/text-input.md). The current operating policy supersedes earlier attempts to discover a universal input-source shortcut:

1. Open the intended field, preserve any existing draft and verify focus after the UI settles. The absence of an on-screen iPhone keyboard is not itself a fault.
2. Copy the complete, committed string on the Mac and try ordinary Command-V once. Inspect the actual rendered text; a field outline or successful tool return is not proof.
3. If the exact text does not appear after the paste/UI settles, ask the user to enter only that text in the prepared field. Do not ask them to send it. Verify their input and resume the remaining authorized work.
4. Keep sending separate from editing. For a no-send test, never press Return or Send. Clear only the synthetic draft you inserted and verify cleanup. Preserve text of uncertain origin.

Earlier native `paste` and `typeText` attempts produced missing letters, Japanese composition or no text. Persistent Mac copy followed by Command-V succeeded in Settings but was not established in the Even composer. The cause remains unknown; do not label it an Even input defect. Do not keep cycling through Control-Space, fn or alternative key combinations during ordinary work.

`super+a` and BackSpace previously cleared synthetic text in the focused field. Escape can dismiss composition, but inspect the result. When the user changes apps or enters text, refresh state before continuing and preserve their content.

## Acceptance evidence

Define one bounded session with the starting route, exact build, concrete operations, expected results and finish condition. Monitor machine-readable state directly; collect only physical-only observations from the wearer after the sequence. Report passed, failed and unverified checks separately. Keep independent defects separate from the original acceptance result.

Read the exact Even version and Mac test artifact/commit separately. A Mac-only test does not require changing Even. Connected status, message receipt, and the phone's rendered content are different evidence from physical G2 display/notification observations. Collect physical-only observations from the wearer once after the agreed bounded sequence. Do not consume pending utterances or fabricate a reply through a tool while testing the normal Dot response path.

### Dot Link project requirements

The following are project-specific requirements carried forward from the original skill, not general Even platform behavior. Apply the target repository’s current instructions and authority.

For Dot Link product-change work, Beta acceptance and merge are intermediate stages. Track the outcome through formal distribution to users, including the affected Mac update feed or Even Hub stages. If a maintainer action or stage-specific approval is still needed, prepare the concrete handoff and report distribution as unfinished. Keep release, upload, review submission, and publication authority separate under the project's current instructions; the maintainer presses the Even review-submission button. This skill grants no additional authorization.
