# Arena Map Veto — Staff Edition

Standalone Windows map-veto tool for FiveM Arena staff. Independent of Arena Tournament Manager.

## Features
- BO1, BO3 and BO5 vetoes, coin flip, picks, bans and side selections
- Eight bundled maps, with seven active by default (**City Hall inactive**)
- Map preview and RED/BLUE spawn images
- Local veto history, editable rotation, backup on destructive operations
- Independent update checks against `staff-vX.Y.Z` releases in this repository

## Building
1. Place **staff_map_assets.zip** in the repository root. It must contain `assets/maps/<slug>/preview.png` and `assets/maps/<slug>/spawns.png` for the eight map slugs in `staff_map_veto.py`.
2. Open **Actions → Build standalone staff map veto → Run workflow**. Leave **publish_release** unchecked for a test build.
3. Download the `ArenaMapVeto-Staff-Windows` artifact and test the Windows executable.
4. After testing, update `VERSION` in `staff_update.py`, then manually run the workflow with **publish_release** checked and a matching version.

The build is manual-only to avoid unnecessary Actions usage.

## Saved data
Local files are kept under `%LOCALAPPDATA%\ArenaMapVeto` and are not removed during updates. A fresh installation populates the default map pool; an existing map library is not overwritten.

## Security
Updates use GitHub release assets with SHA-256 verification. Windows Defender or SmartScreen warnings must be investigated rather than bypassed. Release builds are not yet code-signed.

## Status
Development / Windows testing pending. Do not distribute as a verified release until the updater and map image rendering have been tested.
