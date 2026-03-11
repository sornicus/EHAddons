# _NPCScan Changelog

## ebonhold fork

### Changes vs. original 3.3.5.5

- **Interface version**: Bumped to `30305` for WoW 3.3.5 compatibility.

- **Timer bug fix** (`_NPCScan.lua`): `OnUpdate` was resetting `LastUpdate` (undefined) instead
  of `NextUpdate`, causing the scan loop to run every frame rather than every 0.1 seconds.

- **Per-zone cache tracking** (`_NPCScan.lua`): Replaced permanent mob deactivation on found/cached
  with a per-zone suppression table (`ZoneEntryCached`).
  - Mobs already in the cache when entering a zone are silently noted and skipped during scanning.
  - When a mob is found mid-zone it is suppressed for the remainder of that zone visit only.
  - On `PLAYER_ENTERING_WORLD` the suppression table is wiped, giving every mob a fresh alert
    opportunity in each new zone.
  - Previously, _NPCScan would permanently stop alerting for a mob the first time it was ever
    cached, requiring a manual `/npcscan reset` to restore alerts.
