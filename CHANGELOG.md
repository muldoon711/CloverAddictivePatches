# Changelog

All notable changes to CloverAddictivePatches are documented here.

---

## v1.0.7 — 2026 Game Update Compatibility

Released to restore compatibility after the CloverPit 2026 update broke several patches.

### Fixed
- **Accessibility menu layout** — the game now includes Flashing Lights reduction natively; shifted the mod-injected FOV option from index 5 to index 6 to account for the new native entry
- **`Data.settings` access** — game changed this from a public field to a property; updated all access paths accordingly
- **`PowerupScript.NameGet()` signature** — gained a third `sanitize` parameter in the update; patched call sites updated to match

---

## v1.0.6 and earlier

See [commit history](https://github.com/muldoon711/CloverAddictivePatches/commits/main).
