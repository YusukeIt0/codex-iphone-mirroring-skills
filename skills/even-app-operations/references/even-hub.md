# Even Hub storefront and plugin management

Observed through the Even iPhone app on 2026-10-25. Inspect current labels and let navigation settle before choosing the next control. These are the in-app Hub routes, not the separate Developer Hub website.

## My plugins

Open Even Hub, then the top-right avatar. My plugins shows installed plugin names, versions and per-row Open controls. The top profile row leads to Developer hub. A plugin name opens its store detail; its Open button launches the plugin. The sort menu offered Updates available, Size and Name; Name was selected. A separate direction control is present. Ordering changes were not exercised with only one plugin remaining.

## Store detail versus running plugin

The observed store detail contains the name, short description, developer, category, ranking, screenshot gallery, overview, heart/count and a bottom Open control for an installed plugin. The store-detail ellipsis exposed Live translation and Share. Neither option was executed in this inspection. Do not confuse that menu with the running plugin's host menu.

The running plugin's host ellipsis exposed Uninstall. To remove an explicitly designated plugin:

1. Verify the exact plugin name and open that plugin.
2. Open the host's top-right ellipsis and select Uninstall.
3. Read the confirmation. The observed sheet explicitly states that all related plugin data will be lost and that the operation cannot be undone. Apply the current tool's confirmation requirements at this stage.
4. Only after the required authorization, confirm Uninstall and verify the plugin is absent from My plugins. Inspect any resulting store action separately; do not reinstall as a test without authorization.

After an authorized OcuClaw removal, the store action changed from Open to Get. My plugins initially retained its stale row; returning to the storefront and reopening My plugins refreshed the count and removed the row. Use this refresh before repeating a removal.

Never infer removal from the sheet closing, and never use uninstall as a restart or update method.

## Discovery entry points

The Even Hub tab opens a storefront with a top plugin-search field, a top-right avatar for My plugins, featured cards and a personalized section. Tapping the search field opens a discovery screen with Popular and New ranking tiles plus category tiles: Performance, Lifestyle, Entertainment, Healthcare, Education, AI, Music, Travel and Utilities in the observed Japanese UI. Read live labels instead of relying on this list remaining fixed.

A category tile opens its category page. Search text entry must follow the shared copy/paste-and-user-handoff procedure; opening the field alone does not verify a completed query.

Category pages show a featured area, a plugin count, a list and a sort selector. The observed options were Automatic, Top popular and Latest. Selecting Latest changed the list after a loading spinner finished; the label changing alone was not enough evidence. Restore the original selection after a diagnostic check.

The Popular and New tiles open a shared Ranking page with Popular/New tabs. Both tabs were exercised and displayed different lists. Select a plugin name to inspect details; Get is a separate action and can begin installation. Do not press Get merely to inspect the listing. Heart/count and Share are also separate actions, not navigation controls.

## Observed interaction limits

In a G2Loo detail page, two native vertical-scroll attempts did not move the visible content. A horizontal image drag and an image tap also did not establish gallery navigation or enlargement. Back navigation still worked. Do not assume an entire page is frozen or claim these gestures are verified. Stop repeated attempts and use a narrow user handoff when the hidden content is needed.

Even Hub search displayed an iOS cross-device paste-permission prompt. Confirm the intended source and current task before allowing a prepared non-sensitive string. The observed transfer nevertheless inserted an old clipboard string instead of the copied query; it was cleared using the search field's X. Follow the one-attempt input fallback and ask the user for the query rather than continuing to paste blindly.

The user also reported being unable to enter the intended query manually in this session. The exact cause was not established. Search by entered text therefore remains unverified; category navigation and My plugins remain usable alternatives for their respective tasks.
