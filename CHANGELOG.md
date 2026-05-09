# Changelog

All notable changes to this project will be documented in this file.

## Changes for v0.8

### Changed

- **Subblock tags must be uppercase** (e.g. `REL:`, `APP:`, `RP:`; not `rel:`, `app:`, `rp:`). Documented and exemplified throughout the Polish GRIM specification (`pl/GRIM.md`).
- **Polish spec (`pl/GRIM.md`) — clarity and examples**
  - Default *active* entity wording tightened (significance in play stated up front).
  - Strikethrough section: small wording polish; task vs. strike contrast now uses *zakończone* for completed checklist items.
  - Task/checklist examples: mechanics phrasing and item order in the sample block adjusted.
  - **Progression:** example for striking unused steps now keeps the step number outside the strike: `2. ~~!! Kapitan przybywa~~`.
  - **Entity-symbol headers:** introductory prose shortened; markdown sample shows a regional category with body text, Polish place names, and nested `####` headings for sub-locations and a character under the same region.
- **Optional header emoji** section: prose revised (default is still "no emoji" unless type or scan speed benefits).

### Removed

- **`📝` entity-type emoji** for quests/tasks; tasks are represented only with markdown task markers `- [ ]` / `- [x]`. Removed from the entity emoji table and the emoji index in `pl/GRIM.md`.
