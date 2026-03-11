# VuhDo Changelog

## Ebonhold Patches

### [2.23-1] - 2026-03-11

#### Fixed
- `VUHDO_TIMERS["MIRROR_TO_MACRO"]` was being set inside the `for` loop in
  `VUHDO_refreshRaidMembers`, causing it to execute up to 40 times per roster
  refresh instead of once. Moved to after the loop to match the behavior in
  `VUHDO_reloadRaidMembers`.

---

## Upstream (Iza@Gilneas)

### [2.23]
- Minor bugfixes

### [2.22]
- Fixed frame strata (dim bars)

### [2.21]
- Fixed refresh rate for d/c shield
- Adjusted frame strata (hots, custom debuffs now on top of text)
- Minor bugfixes

### [2.20]
- Fixed range checking for mind controlled units
- Added Cyclone to buff removal spells for mind controlled units
- Blizz standard player/party frames enablement loads from profiles correctly
- Performance optimizations and code cleanup
- Map dimensions no longer persisted to avoid permanent inaccuracies
- Added 2 new HoT positions

### [2.19]
- Added feature to cancel in-progress spellcast and start new cast on repeated click

### [2.18]
- Fixed filters for loose panel setup
- Performance optimizations; throttled map request queries in cluster builder
- Added direction arrow scale slider
- Added options for exporting custom debuffs to profile
- Improved mid-fight login raid panel restoration

### [2.17]
- Fixed HoT positioning bug in rare cases
- Fixed custom debuff indication after profile load
- Fixed direction arrow font initialization
- Performance optimizations; reduced talent tree server queries via dungeon finder roles

### [2.16]
- Fixed mouseover highlight bar orientation bug
- Performance optimizations
- Added direction display for out-of-range players

### [2.15]
- Fixed prohibited function calls mid-fight
- Fixed raid icon bar coloring bug

### [2.14]
- Fixed radio button display in options=>panels=>misc
- Fixed smart cast resurrection with explicit range checking spell
- Fixed custom debuff icon removal

### [2.13]
- Fixed target-of-target and focus target update flaw
- Fixed bar positioning bug
- Fixed lua error after player left vehicle
- Fixed power bars showing with inverted growth direction
- Added Pain Suppression to priest buff watch
- Added bouquet items for class, role and raid target icons
- Bar orientation moved to indicators concept
- Added libDataBroker support

### [2.12]
- Fixed pet with same name as raid player bug
- Fixed cluster scanning with no mouseover bouquet selected

### [2.11]
- Fixed profile load from another toon
- Fixed players not removed from raid roster in some cases
- Fixed button positioning bug
- Fixed cluster scanner with bouquet-only cluster display
- Auto-firing trinkets/instants works for target/focus bars

### [2.10] (merged with 2.9)
- Filter settings no longer affect BuffWatch blessings
- Fixed same zone detection for hot icons
- Fixed single target unique buff target selection
- Smart cast resurrection on by default
- Added cooldown reference spell for cluster scanner
- Added optional player target to private tanks panel
- Added quiet mode for profile saving
- Added custom debuff name display option
