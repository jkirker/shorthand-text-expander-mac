# Shorthand — Features & TextExpander Parity


## 1. Capability inventory

### Expansion
| Capability |
|---|
| Watches typing system-wide (active CGEventTap) and expands abbreviations |
| Expand mode: immediately, at delimiter (keep), at delimiter (abandon) |
| Custom delimiter set |
| What a group's abbreviations must be followed by: whitespace, anything but letters/numbers, any character |
| Case modes: case sensitive, ignore case, adapt to the case typed |
| Longest-match, app-specific-first matching |
| App scopes per group *and* per snippet (all / all except / only / none / default) |
| Insertion via clipboard paste (plain, RTF, optional HTML) with clipboard restore |
| Keystrokes typed during an expansion are held and replayed |
| Expansions are serialized, and ⌘V waits for the clipboard restore |
| Auto-capitalize sentences; double-caps fix (applies in every app) |
| Sounds on expansion |
| Secure Input detection and warning; warning while TextExpander is running |

### Organizing (1.3)
| Capability |
|---|
| Multi-select snippets and groups (⌘/⇧-click), with bulk right-click actions and drag |
| Duplicate snippets (unique abbreviations) and groups (copies start disabled); merge groups |
| Trash with Put Back, Delete Immediately, Empty, and auto-delete after N days |
| ⌘Z / ⇧⌘Z for structural edits (50 steps; cleared by non-undoable changes) (1.3.1) |
| Tags: editor chips, sidebar section with colours and counts, `#tag` filter (main list and Search panel), Tag Manager |

### Privacy (1.3)
| Capability |
|---|
| Blocked apps: no listening at all; password managers by default |
| Blocked websites: host read via Accessibility (off the main thread, time-boxed; Chromium AX switched on; every frame checked); domain, subdomain and keyword rules. Verified in Arc. |
| First-use question per app (Allow / Block; no listening until answered; ignoring for 12 s = allow; running apps seeded on upgrade) |
| Menu bar: Paused here / Allow here / Block app / Block site |

### Security (1.4)
| Capability |
|---|
| Encryption at rest (AES-256-GCM) for library, settings, statistics and backups; key in the Keychain |
| Password slot (PBKDF2 1M) and mandatory recovery key (HKDF); change password; new recovery key |
| App lock: Touch ID / Apple Watch / Mac or Shorthand password; relock on sleep, screen lock or idle; optional expansion pause |
| Locked / unreadable distinction: encrypted data without a key is never treated as damaged |
| Encrypted sync folder: unlock once per Mac |
| "Protect Shorthand?" offer; Settings → Security |

### Distribution (1.5)
| Capability |
|---|
| Automatic updates (Sparkle 2, EdDSA-signed, from GitHub Releases), with Check for Updates… and auto-check/auto-install settings |
| License agreement ("as is", no warranty) accepted once before first use; viewable in Help |
| Public website: downloads, docs, Help site (GitHub Pages) |

### Snippet content (macros)
The full list is in Help › Macro Reference (also on the [Help site](https://jkirker.github.io/shorthand-releases/macros.html)). 
| Family | Codes |
|---|---|
| Fill-ins | `%filltext`, `%fillarea`, `%fillpopup`, `%fillpart…%fillpartend%`, `%filltop%` |
| Dates/times | strftime-style codes (`%Y %m %d %B %e %H %M %p` …), `%date:format%`, date math `%@+15D` |
| Text sources | `%clipboard`, `%snippet:abbr%` (nested, including nested scripts) |
| Keys & cursor | `%key:name%`, `%|`, `%\` (select to here), arrows `%< %> %^ %v` |
| Delimiter | `%+` keep, `%-` abandon |
| Literal | `%%` |
| **Shorthand-only** | `%calc:expr:decimals%`, `%if:cond%…%else%…%endif%`, `%ai:prompt%` |

### Snippet types
Plain text, formatted text (RTF), AppleScript, shell script and JavaScript (JXA). Scripts run in a separate process with a 10-second timeout.

### Library & data
- Import formats:
  - TextExpander `Settings.textexpander` (whole library, including the lifetime "Characters Saved" counter)
  - group `.textexpander` files
  - `.textexpanderbackup` folders
  - CSV/TSV
- Export a group back to a TextExpander-format `.textexpander` file.
- The library is JSON in Application Support, or in a sync folder (Dropbox / iCloud Drive). It reloads automatically when another Mac changes it.
- Switching to a folder that already holds a library asks you to use it or replace it, and backs up the other copy (1.2).
- Automatic backups at launch (keeps the last N), Back Up Now, and Restore.
- Undo for deleting snippets and groups.
- Statistics: expansions, characters saved (plus imported TextExpander history), daily counts, and use counts per snippet.

### UI
- Menu bar menu:
  - groups → snippets
  - suggestions
  - warnings
  - Help
  - Ko-fi
- Main window with a group/snippet list, rich editor, Insert menu for every macro, preview, conflict markers and use counts.
- Search panel (⌘1–9 to pick), and inline search.
- Global hotkeys:
  - open
  - toggle expansion
  - create snippet
  - create from selection
  - create from clipboard
  - edit last expanded
  - inline search
  - search
  - AI Actions
- Setup/onboarding with Accessibility check and import.
- **Help window (1.2):** 19 topics, sidebar, search, links between topics, inline SVG illustrations.

### AI (1.1, multi-provider in 1.2)
- **AI Actions:** select text → ⌃⌥A → pick an action or type an instruction → the result replaces the selection.
- **`%ai:prompt%`:** generated text at the cursor. `{clipboard}` and `{field}` values are filled in first, several prompts run concurrently, and you can keep typing while it works.
- **Suggest with AI:** abbreviation, label, and fill-in template for a snippet. Uses structured JSON: schema on Claude, tools or JSON-in-text on others.
- **12 providers.** The primary can be any of them. An optional fallback is tried once on failure, never on refusal.
- Live model lists per provider, with a type-or-pick model field.
- Thinking effort (low/medium/high). Used by Claude and OpenAI reasoning models.
- Keys live in the Keychain, one per provider. Custom base URLs must be https, or http only to localhost.

### Typing insights (1.1)
- Snippet suggestions from repeated phrases. In-memory SHA-256 counts; only rejected hashes are persisted.
- Reminders when you type out a snippet's full text. Rate-limited to once per 10 minutes per snippet.

### Support (1.2)
- Ko-fi "Buy me a coffee" link (https://ko-fi.com/kirkerplugins). Hidden in `APP_STORE=1` builds.

## 2. TextExpander 5.1.5 parity matrix

Legend:
- ✅ **equal:** the same feature.
- ➕ **better:** Shorthand does more.
- ◐ **partial:** only part of it.
- ❌ **not supported:** missing.

| TextExpander 5 feature | Shorthand | Notes |
|---|---|---|
| Runs natively on Apple Silicon / macOS 28 | ➕ | TE5 is Intel-only (Rosetta). Shorthand is arm64. |
| Abbreviation expansion, delimiters, expand-immediately | ✅ | |
| Case sensitive / ignore / adapt | ✅ | |
| "Expand after" per group | ✅ | |
| Group app exceptions (all/except/only/none) | ➕ | Also available per snippet. |
| Plain and formatted (RTF) snippets | ✅ | Images inside RTF are untested; none were in the TextExpander libraries it was tested with. |
| AppleScript / shell / JavaScript snippets | ➕ | Run asynchronously with a timeout, so typing never freezes. |
| Fill-ins: text, area, popup, optional section | ✅ | |
| `%filltop%` | ✅ | Implemented in 1.2. |
| Date codes and date math | ✅ | |
| Clipboard, nested snippets, `%key:`, cursor, select-to, arrows | ✅ | |
| Keep/abandon delimiter (`%+` / `%-`) | ✅ | |
| Search hotkey, inline search | ✅ | |
| Create from selection/clipboard, edit last expanded | ✅ | |
| Suggested snippets | ➕ | Privacy-safe: only hashes are stored, and it's opt-in. TE's captured text is skipped on import. |
| Statistics | ➕ | Imports TE's lifetime "Characters Saved". |
| Sounds | ✅ | |
| Dropbox/iCloud sync | ◐ | Whole-file sync with reload and conflict prompt. No per-group sync folders. |
| Backups / restore | ✅ | |
| Auto-capitalize, double-caps correction | ✅ | |
| Import TE libraries | ✅ | |
| Export group in TE format | ✅ | |
| Groups subscribed from a URL (remote/shared groups) | ❌ | Not implemented. |
| TextExpander touch / iOS sync | ❌ | Future idea (docs/TODO.md). |
| Conditional text, calculations | ➕ | `%if`, `%calc`. |
| Multi-select, bulk move/delete | ➕ | Plus duplicate, merge, drag to group/tag/Trash. |
| Trash / restore deleted snippets | ➕ | TE5 deletes immediately (backups only). |
| Tags | ➕ | TE5 has groups only. |
| Encryption at rest + app lock | ➕ | TE5 stores its library as a plain file. |
| App/website blocklist | ➕ | TE5 has per-group app exceptions only. Shorthand also blocks websites and stops listening entirely. |
| AI (rewrite, generate, suggest) | ➕ | 12 providers with fallback. |

**Flags.** TE5 parity is checked against TE5's bundled help and the TextExpander libraries it was tested with, not against every TE5 setting. TE5 settings that aren't in the help, or that the TextExpander libraries it was tested with didn't use, may be missing. See docs/TODO.md.