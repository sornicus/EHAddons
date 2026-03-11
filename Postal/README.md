# Postal

**Enhanced Mailbox support for World of Warcraft 3.3.5 (WotLK)**

Maintained fork by **Ebonhold** — originally authored by Xinhuan.
Repository: `Ebonhold/Addons`

---

## Overview

Postal improves nearly every aspect of the WoW mailbox — bulk opening, smart filtering, contact autocomplete, mouse shortcuts, and more. All features are implemented as independent modules that can be toggled on or off individually from the Postal menu button in the top-right corner of the mailbox window.

---

## Modules

### OpenAll
Adds an **Open All** button to the inbox that batch-collects attachments and gold from all mail automatically.

- Configurable filters per mail type (AH cancelled, expired, outbid, sold, won, pending; Neutral AH variants; player attachments)
- Shift-Click the button to override all filters and open everything
- Skips CoD mail and GM mail unconditionally
- Configurable opening speed (0.30s – 5.00s per operation)
- Keeps a minimum number of free bag slots before stopping
- Verbose mode toggle (chat spam on/off)

### Select
Adds **checkboxes** to each inbox row for fine-grained batch operations.

- Check individual mails then click **Open** or **Return** to process only those
- Shift-Click two checkboxes to select every mail between them
- Ctrl-Click a checkbox to select/deselect all mail from that sender
- Same CoD/GM skip rules and bag-space protection as OpenAll

### Express
Mouse shortcut enhancements for reading and composing mail.

- **Shift-Click** a mail to instantly take its item or money
- **Ctrl-Click** a mail to return it to sender
- **Alt-Click** an item in your bags to attach it to the current outgoing mail
- **Mouse wheel** scrolls the inbox list

### BlackBook
Contact list and autocomplete for the **To:** field when composing mail.

- Tracks the last 10 recipients automatically
- Stores a manual contacts list
- Autocompletes from: contacts, recent recipients, friends list, guild roster, and alts
- Supports Ctrl-Click alt management
- Option to disable Blizzard's default autocomplete

### Wire
Automatically sets the subject line of outgoing mail to the coin amount being sent when no subject is typed.

### Rake
Prints the total gold collected at the end of each mailbox session to chat.

### TradeBlock
Blocks incoming trade requests while the mailbox is open, preventing interruptions during batch mail operations.

### DoNotWant
Displays a clickable icon on each inbox item showing whether the mail will be **returned** or **deleted** on expiry. Lets you delete unwanted mail directly from the inbox without opening it.

---

## Installation

1. Copy the `Postal` folder into:
   ```
   AppData\Local\ebonhold\Interface\AddOns
   ```
2. Log in and open a mailbox — the addon loads on demand when the mailbox opens.
3. Click the small arrow button in the top-right of the mailbox to access Postal's menu.

---

## Configuration

All options are accessible from the **Postal menu button** (small arrow, top-right of mailbox):

| Menu Item | Description |
|---|---|
| Module toggles | Enable/disable each module independently |
| Opening Speed | How fast OpenAll cycles through mail (0.30s – 5.00s) |
| Profile | Create, switch, copy, reset, or delete saved setting profiles |
| Help | View module descriptions and version info |

Per-module sub-options (filters, keep-free-space, verbose mode) are available by hovering the arrow on each module entry.

---

## Known Private Server Behaviour

This fork includes targeted fixes for private server quirks:

- **OpenAll stall fix** — if the server does not acknowledge a taken item or gold after 10 timer cycles (~5 seconds at default speed), Postal will print a warning and advance to the next mail rather than freezing
- **AHPending delete fix** — deleting Sale Pending mail no longer waits for a `MAIL_INBOX_UPDATE` event that may never arrive on some servers
- **AH faction detection** — checks both localized and English faction names when classifying AH mail, preventing mis-filtering on servers with English NPC names

---

## Dependencies

Bundled (no separate install needed):

- LibStub
- CallbackHandler-1.0
- AceAddon-3.0
- AceEvent-3.0
- AceDB-3.0
- AceHook-3.0
- AceLocale-3.0

---

## Localization

Supported locales: `enUS`, `ruRU`, `frFR`, `esES`, `zhTW`, `zhCN`

---

## Credits

- **Xinhuan** — original author
- Ammo, Rabbit, Grennon, Mikk — original contributors
- **Ebonhold** — private server maintenance and reliability fixes
