# Changelog

> Doc version 1.7.6 · Last updated 2026-11-08

All notable changes to Shorthand Expander™. Format: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/). Versioning: [SemVer](https://semver.org/).
Dates are local (Pacific).

## [1.7.6] — 2026-11-08

### Changed
- **Shorthand Expander™:** the app now uses its official name in the About window, the welcome window, the main window title, the license agreement, and Help.

## [1.7.5] — 2026-11-08

### Added

## [1.7.4] — 2026-11-08

### Added
- **Hotkey checks:** when you record a hotkey in Settings ▸ Hotkeys, Shorthand refuses one that another Shorthand action or macOS already uses, says what uses it, and warns about combinations most apps use (⌘ or ⌃ with a single letter). If macOS refuses a hotkey because another app holds it, Settings says so.
- **Jump to the filter:** Edit ▸ Filter Snippets (⌘F, or ⌃F) puts the cursor in the Filter field above the snippet list.

## [1.7.3] — 2026-11-08

### Fixed
- **Crash when setting a hotkey:** recording a hotkey in Settings ▸ Hotkeys (for example ⌃F) quit Shorthand. Hotkeys now record normally, and F1–F20 show their correct names.
- **Template Packs:** packs that use AI now say you can turn on Apple Intelligence or set up a provider, and don't show the setup hint when AI is already working.

## [1.7.2] — 2026-11-06

### Changed
- **90 days free for every new user:** after early access ends (March 31, 2027), the full-feature trial is 90 days instead of 14. If you installed during early access, your 90 days start on March 31, 2027.

### Fixed
- **Ask before snippets can reach the cloud:** with Apple Intelligence as your provider and a cloud fallback, Reply using my snippets and Translate Group now ask once before sending snippets, because a failed on-device request goes to the fallback.

## [1.7.1] — 2026-11-06

### Changed
- **Early access extended:** every Pro feature is now free for everyone until March 31, 2027. Then a 14-day trial (90 days from 1.7.2).
- **Settings button:** a gear at the top right of the main window opens Settings.
- **AI works with no setup:** if you haven’t set up an AI provider and Apple Intelligence is on, Shorthand uses it automatically. A provider you’ve set up is never overridden. Settings ▸ AI shows when this is happening.
- **Apple Intelligence help:** when Apple Intelligence is off or still downloading, Settings ▸ AI shows step-by-step instructions, an Open System Settings button, and Check Again. AI features say the same and offer the button, instead of a general "set up a provider" message.

## [1.7.0] — 2026-11-06

### Added: AI
- **Apple Intelligence (on this Mac):** a new AI provider with no key and no account. Nothing leaves the Mac. Needs macOS 26 or later with Apple Intelligence turned on.
- **Fill from Clipboard:** in the fill-in window, AI fills the fields from text you copied (for example, a name and order number from an email).
- **Reply using my snippets:** an AI Action that writes a reply to a selected message from your most relevant snippets, and copies it.
- **Tone by app:** AI Actions and `%ai` snippets write in the tone you set for each app or website.
- **Translate Group:** a translated copy of a group, with fill-ins, dates, and other codes kept intact.
- **Review Kept Codes with AI:** after an import, AI suggests Shorthand versions of another app's leftover codes; every suggestion is checked and you choose which to apply.
- **AI assistants (MCP):** Claude Desktop, Claude Code, Cursor, and other MCP apps can search your snippets and fill them in. Off by default, read-only, never shares scripts, `%ai`, the clipboard, or private groups, and stops while Shorthand is locked.
- **Never send to AI:** a group setting that keeps a group out of features that use your library.

### Added: on this Mac
- **Search by meaning:** the search window also finds snippets by what they mean, using Apple's on-device language tools. Nothing is sent anywhere.
- **Tune Up Library** (File menu): duplicates, near-duplicates, abbreviations that get in each other's way, never-used and empty snippets.

### Added: Teams
- Share snippet groups with up to 5 people or Macs through a folder the team already shares, with no account or server. Admins sign everything they share; members' Macs verify it. Optional team password encrypts the shared snippets. Settings ▸ Team has the admin panel (shared groups, members and seats, admins, team details, security). `%team:Name%` inserts a team detail.

### Added: Shorthand Pro
- **Free and Pro editions.** Free covers everything for typing on your Mac. Pro ($29 a year, up to 5 Macs or people) adds AI, Teams, AI assistants, script snippets, calculations and conditions, sync across Macs, and Pro template packs. See Help ▸ Shorthand Pro and Licenses.
- **Early access:** every Pro feature is free for everyone until January 31, 2027. Then a 14-day trial.
- **Settings ▸ License:** add or remove a license code. Codes are checked on your Mac; nothing is sent anywhere. Without Pro, Pro features pause and your snippets keep working.

### Added: iPhone and iPad
- Export ▸ **Text Replacements for iPhone and iPad:** plain snippets as macOS Text Replacements, which sync to iPhone and iPad through your iCloud.

### Changed
- AI Actions have a "Use tone by app" option; translation and spelling actions skip it by default.

## [1.6.1] — 2026-11-05

_Not released separately; these changes ship in 1.7.0._

### Added
- **More apps to import from** (File ▸ Import Snippets…):
  - **aText:** `.atext` library files and aText's JSON export. Groups, abbreviations, labels, and text come across; aText's own variables stay as text.
  - **TypeIt4Me:** `.typeit4me` set files, with dates, date math, the clipboard, Tab/Return/Delete keys, the cursor, and AppleScript snippets converted.
  - **Rocket Typist:** `.rtfolder` and `.rockettypist` exports, with dates, text fields, option menus, nested snippets, keys, and JavaScript snippets converted.
  - **Text Blaze:** the dashboard's folder export (`.json`), with the clipboard, cursor, dates, form fields, menus, toggles, imported snippets, and keys converted.
- **Typinator:** spreadsheet exports that use Typinator's codes now convert dates, date math, the clipboard, the cursor, Tab and Return, simple input fields, and other abbreviations.

### Security
- Importing a damaged or doctored file can no longer create unexpected objects (aText files are now read with Apple's secure decoding) or exhaust memory (aText 3 decompression is capped at 64 MB).
- New stress tests feed every importer thousands of damaged files and random code mixtures.

### Changed
- Help ▸ Importing Snippets lists every supported app, including how to bring snippets from Typinator (its spreadsheet export) and why PhraseExpress can't be imported.

### Website
- A switching hub at shorthandexpander.com/switch with step-by-step guides for TextExpander, aText, TypeIt4Me, Rocket Typist, Text Blaze, Espanso, Raycast, Alfred, macOS Text Replacements, and other apps.

## [1.6.0] — 2026-11-05

### Added
- **Template Packs** (File ▸ Template Packs…, or + below the group list): 9 ready-made groups with 57 snippets: Email essentials, Customer support, Dates & times, Symbols & keys, Meetings & notes, AI writing assistant, AI for support teams, Developers, and Smart calculations. Adding a pack creates a new group; abbreviations you already use get a number instead of being replaced.
- **Import from other apps:** File ▸ Import Snippets… (⇧⌘I, formerly Import TextExpander Snippets…) now also reads Espanso match files and folders, Raycast and Alfred snippet exports, macOS Text Replacements, and CSV or tab-separated files with a header row (for example, exports from aText, TypeIt4Me, Typinator, PhraseExpress, Text Blaze, and Rocket Typist). Their clipboard, cursor, date, and fill-in placeholders are converted; anything without an equivalent is kept as text, and Shorthand tells you how many.
- **Export Snippets** (File ▸ Export Snippets…, ⇧⌘E): every group, or just the selected ones, as Shorthand JSON (complete and re-importable), CSV, TextExpander group files, Espanso, or Raycast. Exports are plain, unencrypted files.
- **shorthandexpander.com:** Shorthand's new home, with the full help center, comparisons with other text expanders, and release notes by email. Help ▸ Shorthand Website & Downloads and the links in Help now go there.

### Changed
- Help and the app now use US English throughout (for example, the tag menu's **Colour** is now **Color**).
- The license agreement names John Kirker Inc. and gives a support address. Its terms are unchanged.

### Help
- New topics: Template Packs and Exporting Your Snippets. Importing from TextExpander is now Importing Snippets, with a section on other apps.
- New screenshots (light and dark): Settings ▸ Expansion, Settings ▸ Options, Settings ▸ Hotkeys, Create Snippet, Template Packs, and Export Snippets.

## [1.5.4] — 2026-11-01

### Fixed
- **Typing and clicking could freeze system-wide** (scrolling still worked) if Shorthand's Accessibility access was turned off in System Settings while it was running. Shorthand now notices within a fraction of a second and fully stops its keyboard monitor.
- **Reset Permission & Ask Again** now stops the keyboard monitor before removing access, so it can't cause the same freeze.

## [1.5.3] — 2026-11-01

### Changed
- Shorthand's home on GitHub is now **github.com/jkirker/shorthand-text-expander-mac**, a name that says what it is. The online help moved to **jkirker.github.io/shorthand-text-expander-mac**.
- Updates, the Help ▸ Shorthand Website & Downloads menu item, and links in Help use the new address. Older versions keep updating through GitHub's automatic redirect.

## [1.5.2] — 2026-11-01

### Added
- **Disk image download.** `Shorthand-x.y.z.dmg` opens a window with Shorthand and an Applications shortcut to drag it onto. It's signed, notarized and stapled like the app; the zip is still provided for automatic updates.
- **Uninstall Shorthand…** in Settings ▸ General: "keep my snippets" or "delete everything" (asks twice). A synced library is never deleted.
- **Dark mode screenshots** throughout the Help and on the website. They follow your Mac's appearance.

### Changed
- **Automatic update checks are on by default** (once a day), so there's no extra prompt. Background checks show a gentle reminder, and the update window always comes to the front. Previously a manual check could open it behind other apps.
- Update downloads are verified before they're unpacked.
- Running Shorthand straight from Downloads (macOS "translocation") shows a tip to move it to Applications, and no longer changes the login item each launch.

### Fixed
- Declining the license agreement no longer loads or writes any data.
- The Dock icon goes away after the license, update and other windows close.

### Release process (developer)
- `release.sh` refuses to publish unless:
  - the app and zip are the notarized Developer ID build, with matching build numbers
  - the Sparkle key in the Keychain matches the key built into the app
  - the signature verifies
- Failed feed or download checks stop the script, and leftover drafts are cleaned up.
- The install step waits for the old copy to quit, and installs only Developer ID builds.

## [1.5.1] — 2026-11-01

### Added
- **Help ▸ Shorthand Website & Downloads** opens the Shorthand page on GitHub, with downloads, release notes and the online help.
- **Help pages:** the license agreement (Getting Started), updates and the license (Support Shorthand), and what update checks send (nothing about you; see Privacy).

### Notes
- This is the first update delivered through automatic updates. If you're on 1.5.0, Shorthand offers it on its own.

## [1.5.0] — 2026-11-01

### Added
- **Automatic updates.** Shorthand checks for new versions, shows what's new, and installs with one click.
  - Find it under Shorthand ▸ Check for Updates…, the menu bar menu, and Settings ▸ General ▸ Updates (check automatically, or download and install automatically).
  - Updates come from the GitHub releases of jkirker/shorthand-text-expander-mac.
  - Each update is verified twice before installing: by the developer's Sparkle signature and by the same Developer ID.
- **License agreement.** It's shown once before Shorthand starts and must be accepted ("as is", no warranty). You can read it any time under Help ▸ License Agreement.

### Changed
- Releases are published with one command: `./scripts/release.sh`.

## [1.4.1] — 2026-11-01

### Added
- `INSTALL=1 ./scripts/build.sh` copies the signed (and, with `NOTARIZE=1`, notarized) app to **/Applications/Shorthand.app**, then relaunches it.
- "Launch at login" re-registers automatically when Shorthand has moved (for example, from the build folder into /Applications). This happens only after a move, to avoid repeated system notices.

### Changed
- Self-test and screenshot modes write their diagnostics to their temporary folder, never to the real log.
- Shorthand now runs from /Applications on the developer's Mac. Moving it kept the Accessibility permission, which is tied to the Developer ID team and app ID.

## [1.4.0] — 2026-11-01

### Added
- **Encryption at rest (optional).**
  - The library, settings, statistics and every backup are encrypted with AES-256-GCM.
  - **One random data key opens everything.** It's kept in this Mac's Keychain and wrapped in a **password slot** (PBKDF2-SHA256, 1,000,000 rounds) and a mandatory **recovery key** slot (a 128-bit code, HKDF).
  - **The recovery key** is shown once, with Copy, Save to File… and Print…, and a required "I've saved my recovery key" checkbox.
  - **Turning encryption on or off** converts every file and backup.
- **App lock (optional).** Unlock with Touch ID, Apple Watch or the Mac password. Optionally, a separate Shorthand password replaces the Mac password.
  - **While locked:** the library, Settings, Setup, Tag Manager, Statistics, Create Snippet and Search are closed and can't be opened, and the menu bar hides snippet names.
  - **Lock again** on sleep or screen lock, after 5, 15 or 60 idle minutes, or only at quit.
  - **Optional:** expansion pauses while locked.
  - **Lock Now / Lock Shorthand** in Settings and the menu bar.
- **The "Protect Shorthand?" offer** on first use, and once after updating. Its choices: encrypt (recommended), require unlock, pause expansion, separate password.
- **Settings → Security** tab.
- **Encrypted sync between Macs.** Choosing an encrypted sync folder on another Mac asks for the Shorthand password or recovery key once. If another Mac re-encrypts the library, saving pauses and a bubble asks you to unlock.
- **Restoring a backup made with an earlier key** asks for the password or recovery key that was in use then.
- **Self-tests** that run the real app code against throwaway data: `--security-selftest` (24 checks), and `--security-selftest-prepare` / `--security-selftest-launch` (9 checks).
- **Help:** a new Security & Encryption topic, with 4 new screenshots.

### Changed
- File loading tells **ok / missing / locked / unreadable** apart. **A library encrypted with a key this Mac doesn't have is never treated as damaged, moved aside, overwritten or backed up.**
- Turning encryption on, off or adopting a key is ordered so an interruption can't strand data: key, then settings, then files, then the old key. An old key is deleted only after every file it opened has been converted.

### Fixed before release (independent security review, 13 findings)
- **A planted slot could open with any password.** A slot with 0 rounds made PBKDF2 fail silently and derive an all-zero key. Slots are now validated (sizes, 100k–10M rounds), the KDF status is checked, and the file header is authenticated (AAD).
- **An empty library could overwrite the real one** after unlocking while the synced file was missing (not downloaded yet) or damaged. Unlocking now stays locked for a missing file, and a damaged file is set aside.
- **A damaged file with the right key was treated as "locked"**, leaving the app stuck. It's now "unreadable": set aside, then restore a backup.
- **Passwords and recovery keys now stay in step across Macs** (slot generation).
- **A Keychain error no longer reads as "wrong password".** The Keychain item is updated in place, and unlocking proceeds for the session with a warning.
- **Keys are retired, not deleted,** so older backups and other Macs' files stay readable. Switching sync folders adopts the folder's key only after you choose "Use Library in Folder", and re-encrypts the current library too.
- **Turning encryption on with another Mac's encrypted sync folder** is refused, so two keys can't compete.
- **Turning off** checks the library really is plain before reporting success.
- **If another Mac re-keys the library,** windows close (edits can't be saved) and the bubble shows once.
- **The "Protect Shorthand?" choices apply only after "Done",** and closing the window brings the offer back next launch.
- **While locked,** ⌘N, New Group and the Trash bubble's Undo require unlocking.
- **With a sync folder,** turning on encryption first asks you to confirm every Mac runs 1.4+; an older Mac would replace the encrypted library with a starter one.
- **Small fixes:** the Dock icon now disappears after the Unlock or Protect window closes; Turn On with an existing password asks for it once (not "new password"); relocking with expansion paused shows a reminder.
- **Passwords are normalized to NFC**, so the same password typed different ways always matches.

### Notes
- Security.json is plain on purpose: settings plus wrapped key slots, no secrets.

## [1.3.2] — 2026-11-01

### Added
- **Developer ID signing and Apple notarization.**
  - Builds are signed with "Developer ID Application: John Kirker (J9P2EN8MW4)", with the hardened runtime and a secure timestamp.
  - `NOTARIZE=1 ./scripts/build.sh` notarizes and staples the app, and writes `build/Shorthand-<version>.zip`, which opens on any Mac without security warnings.
  - The first submission (1.3.1 code) was accepted on 2026-11-01.
- `scripts/Shorthand.entitlements`, with Apple Events for AppleScript snippets under the hardened runtime.

### Changed
- The Accessibility grant is now tied to the Developer ID team, so it survives rebuilds and certificate renewals. Switching from the self-signed identity needs **one** final re-grant (menu bar → Fix…). macOS may also ask once whether Shorthand can use each saved AI key: choose Always Allow.

## [1.3.1] — 2026-11-01

### Added
- **⌘Z / ⇧⌘Z for library changes**, up to 50 steps:
  - moves, duplicates, Move to Trash, Put Back, Delete Immediately, Empty Trash
  - tag add/remove/rename/delete
  - Merge Groups

  Text fields keep their own undo. Undo history is cleared by any change that isn't undoable: snippet text, group settings, import, restoring a backup, switching sync folder, sync reload, reordering or creating snippets. So ⌘Z can never roll those back.
- **Tag filter in the Search panel.** `#tag` words filter (all must match), plain words also match tag names, and results show tag chips.
- **Real screenshots in Help** (9 images). They're made by a new `Shorthand --capture-help-screenshots <dir>` mode that renders Shorthand's own windows with a demo library in a temporary folder. It needs no Screen Recording permission and never touches your data.

### Fixed (independent review of 1.3.0)
- **Typing can't stall.** Browser page lookups now run off the main thread, with a 0.1 s Accessibility timeout per element and a 0.4 s budget per lookup. Previously a busy browser could delay keystrokes system-wide.
- **Websites in Chromium browsers now work.** Chrome, Edge, Brave and Arc only build their web accessibility tree on request, so Shorthand now asks for it (`AXManualAccessibility`). Verified in Arc.
- **Embedded login forms are caught.** Every frame on the focused path is checked, so an iframe login on a blocked site is blocked.
- **No stale page address.** A failed quick lookup no longer reuses an old host; it schedules a fresh deep lookup. Return also triggers a re-check.
- **No listening before you answer.** Shorthand doesn't listen in a new app until its first-use question is answered (no answer within ~12 s = Allow).
  - Apps already open the first time 1.3.1 runs count as answered, so upgrading doesn't ask about every app.
  - The question waits instead of covering a bubble that has an Undo button.
- **The Trash bubble's Undo** acts only if nothing changed since the delete. Before, it could undo "Empty Trash" or a different delete.
- **Syncing with a Mac still on 1.2** no longer wipes this Mac's Trash and tags. They're kept, written back, and a warning is shown.
- **Hidden snippets are never acted on.** Delete and right-click use only visible rows, and the selection is trimmed when the filter or a move hides snippets. Before, ⌘A, filter, ⌫ trashed the hidden ones too.
- **Merge Groups** asks first and keeps each source group's app rules. Snippets from disabled groups are set to "No Applications".
- **Selection fixes:**
  - ⌘N with Trash or a tag selected; Edit Last Expanded inside a multi-selection; Tag Manager "Show Snippets"; suggestions.
  - Deleting groups resets the selection.
  - The Trash list and detail pane share one selection, which resets on leaving the Trash.
  - Renaming a tag keeps the sidebar highlight when it merges.
- **Tags:** renaming onto a tag that's only used (not defined) now asks before merging. Removing a tag no longer leaves an unused tag behind.
- **Smaller fixes:**
  - Faster lists with large selections.
  - Accessibility values are type-checked.
  - Zero compiler warnings, including a Swift 6 concurrency warning in the script runner.
- **Layout:**
  - The AI key row was cut off. "Test key & load models" now has its own row.
  - The fill-in window showed optional sections' names twice and had a gap above the Preview.
  - The Privacy website field showed its hint as a label.

## [1.3.0] — 2026-11-01

### Added
- **Multi-select.** ⌘-click or ⇧-click snippets, and groups in the sidebar. Right-click acts on the whole selection.
  - Snippets: Duplicate, Move to Group (including New Group…), Tags, Move to Trash.
  - Groups: Duplicate, Export, Enable/Disable, Merge Groups into One, Move to Trash.
- **Several groups (or tags) at once.** Their snippets are listed together, each labeled with its group. Selections can be dragged onto a group, a tag or the Trash.
- **Duplicating groups.** Copies start disabled so their abbreviations don't clash with the originals.
- **Trash.** Deleting moves snippets and groups to a Trash in the sidebar, alongside the 8-second Undo bubble.
  - Put Back returns an item to its original group, recreating the group if it's gone.
  - Delete Immediately and Empty Trash… remove items for good.
  - Settings → General → Trash deletes items automatically after 7/14/30/60/90 days or never (default 30). The check runs at launch, hourly, and when the setting changes.
- **Tags.** Add them in the editor's Tags row. The sidebar has a Tags section with colors and counts, and the filter accepts `#tag`. A snippet created while a tag is selected gets that tag.
- **Tag Manager** (Window ▸ Tag Manager, ⇧⌘T): rename (renaming onto an existing tag merges the two), color, merge several, delete (the snippets are kept), add.
- **Privacy blocklist.** In blocked apps and on blocked websites, keystrokes pass through untouched: nothing is buffered, matched, counted or suggested.
  - Password managers are blocked by default.
  - Website domains are read through Accessibility in Safari, Chrome, Arc, Edge, Brave, Firefox, Opera, Vivaldi and Chromium.
  - There's a one-click list of common banking and finance sites to add.
  - The menu bar shows "⏸ Paused here", "Allow Shorthand Here", "Block Shorthand in <app>" and "Block Shorthand on <site>".
- **New-app question.** The first time an app is used, Shorthand asks "Use Shorthand in <app>?" with Allow and Block. Ignoring it means Allow. It can be turned off in Settings → Privacy.
- **Settings → Privacy tab.**

### Changed
- "Delete" is now "Move to Trash" everywhere. Deleting a pending suggestion still discards it, and it isn't suggested again.
- Settings → AI: the fallback clears when it's set to the same provider as the primary.

### Data
- `Library` gains `trash` and `tags`; `Snippet` gains `tags`.
- `Preferences` gains `trashRetentionDays`, `blockedApps`, `blockedDomains`, `askForNewApps` and `knownApps`.
- All of them decode leniently, so 1.2 files open unchanged. Older builds ignore the new keys, but **an older build that saves the library drops its Trash and tags.**

## [1.2.0] — 2026-11-01

### Added
- **Multi-provider AI.** 12 providers, matching the Stetwell plugin's picker:
  - Claude (Anthropic, the default) uses the native Messages API.
  - These use the OpenAI-compatible API: ChatGPT (OpenAI), Gemini (Google), OpenRouter, Groq, Together AI, Mistral, DeepSeek, Kimi (Moonshot), Grok (xAI), Hugging Face (router).
  - Custom OpenAI-compatible: Ollama, LM Studio and similar.
- **Fallback provider.** It's optional and tried once when the main provider fails (bad key, outage, rate limit, network). It's never tried when a model declines a request.
- **Live model lists.** "Test key & load models" calls each provider's `/models` endpoint. The model field lets you pick from the list or type any model id. Lists are cached in preferences, and loaded automatically when a key is already saved.
- **Per-provider API keys in the Keychain.** Keys stored for any provider other than Anthropic go under accounts named `api-key-<provider>`.
- **Retry in plain form on HTTP 400.** If a model rejects an optional parameter (effort, structured output, tools, server-side fallback), the request is retried once without them.
- **In-app Help.** Help › Shorthand Help (⌘?) has 19 topics with a sidebar and full-text search. Pages live in `Resources/Help`. It's also reachable from the menu bar icon menu, Settings → General, and the "?" in Settings → AI.
- **Ko-fi "Buy me a coffee" link.** It uses the official Ko-fi image and appears in:
  - the Help menu
  - the menu bar icon menu
  - Settings → General
  - the Help sidebar and the Support help page

  `APP_STORE=1 ./scripts/build.sh` hides it (Info.plist `ShorthandShowSupport` = false).
- **Stable code signing.** `build.sh` signs with a self-signed "Shorthand Signing" identity kept in a dedicated keychain (`~/Library/Application Support/ShorthandSigning`), so macOS keeps the Accessibility permission across rebuilds.
- **Permission status you can see.** The menu bar menu shows "✓ Keyboard access OK", or a "Fix…" warning when macOS blocks the keyboard. Settings → General → Permissions shows Accessibility, keyboard monitor and Input Monitoring status. "Reset Permission & Ask Again" (`tccutil reset`, Shorthand only) clears a stale grant left by an older build. State changes are written to `~/Library/Application Support/Shorthand/diagnostics.log`.
- **`%filltop%` now works.** The fill-in window opens at the top center of the screen. In 1.1 the code was accepted but ignored.

### Changed
- AI error messages name the provider instead of always saying "Claude".
- Settings → AI is laid out like Stetwell:
  - Provider, API key, model and Thinking effort.
  - A Fallback section.
  - A privacy note naming "the provider you picked".
- Settings → Options now says correctly that capitalization fixes apply in every app.
- `build.sh` defaults `VERSION` to 1.2.0 and bundles `kofi.png` and `Help/`.

### Fixed
- **Choosing a sync folder could overwrite a library that was already there.** Example: setting up a second Mac. Shorthand now asks either "Use Library in Folder" or "Replace with This Mac's", and backs up the copy it sets aside. It never silently overwrites.
- The Ko-fi image path in the Support help page now points inside `Help/`, the only folder the help viewer may read.

### Migration
- An Anthropic key saved by 1.1 keeps working: same Keychain account, `anthropic-api-key`.
- The 1.1 `aiModel` setting is copied into `aiModels["anthropic"]` and kept in step for older builds.

## [1.1.0] — 2026-10-31 (polish on 2026-11-01)

### Added
- **AI Actions palette** (⌃⌥A): rewrite selected text in any app with a preset or your own instruction.
- **`%ai:prompt%` macro.** Generated text is inserted at the cursor, and you can keep typing while it works.
- **Suggest with AI** in the editor and the Create Snippet window: abbreviation, label, and fill-in fields.
- **Snippet suggestions** from phrases you type repeatedly. Only hashes are kept, and suggestions are off by default.
- **Reminders** when you type out a snippet's full text.
- `%calc:…%` math with fill-in values, and `%if…%else%…%endif%` conditional text.
- **Per-snippet "Expand in" app scopes.** The same abbreviation can expand differently in different apps.
- Lenient library/preferences decoding. An unreadable library is moved aside, never overwritten.
- *(2026-11-01)* Undo for deleting snippets and groups.
- *(2026-11-01)* Sync-folder reload when another Mac changes the library.
- *(2026-11-01)* A warning while TextExpander is still running.
- *(2026-11-01)* TextExpander's lifetime "Characters Saved" is carried into Statistics on import.

### Changed
- Import moved to ⇧⌘I, because ⌘I is Italic.
- Use counts are stored in `Statistics.useCounts`, so the library file is no longer rewritten on every expansion.

### Fixed (independent review
- Script snippets no longer block typing. They run asynchronously with a real 10-second timeout.
- A canceled expansion in "immediately" mode restores the swallowed keystroke.
- Expansions are serialized, so overlapping ones (e.g. while AI is working) can't scramble text or the clipboard.
- ⌘V pressed right after an expansion waits for the clipboard to be restored.
- ⇧Return / ⇧Tab delimiters keep Shift. This matters in Slack, where plain Return sends.
- ⌥⌫ resets the abbreviation buffer. The buffer boundary after an expansion is fixed.
- The fill-in window no longer leaks memory. HUD messages no longer hide each other.
- Snippets don't expand inside Shorthand's own search and AI panels.
- First-launch crash (recursive lock during preferences migration).

## [1.0.0] — 2026-10-31

### Added
- A native arm64 app (`com.kirker.shorthand`) for macOS 14+, running without Rosetta.
- **Imports TextExpander:** `Settings.textexpander`, single-group `.textexpander` files, `.textexpanderbackup` folders, and CSV/TSV. The auto-captured "Suggested Snippets" group is skipped by default.
- All TextExpander 5 macros the TextExpander libraries it was tested with uses:
  - fill-ins (text, area, popup, optional part, top)
  - dates and date math
  - clipboard
  - nested snippets
  - `%key:`
  - cursor and selection
  - arrows
  - delimiter keep/abandon
  - `%%`
- **Expansion modes:** immediately, or at a delimiter (keep or abandon). Each group sets what an abbreviation must be followed by. Case modes: sensitive, ignore, adapt.
- **Insertion:** clipboard paste (RTF/HTML) with save and restore.
- **Interface:**
  - main window and editor
  - menu bar menu
  - search panel (⌘1–9)
  - inline search
  - global hotkeys
  - create from selection or clipboard
  - edit last expanded
- **More features:**
  - sounds
  - AppleScript, shell and JavaScript snippets
  - statistics
  - automatic backups
  - sync folder
  - launch at login
  - auto-capitalize and double-caps fixes