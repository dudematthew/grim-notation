# Changelog

All notable changes to this project will be documented in this file.

## Changes for v0.9

### Added

- **Modifiers `^` and `^^`** in the Polish GRIM specification (`pl/GRIM.md`):
  - `^` — *uzupełnienie po sesji*: placeholder for an entity or layer to finish after play, when player actions and choices define the final wording.
  - `^^` — *opracowanie przed sesją*: placeholder when details are written first and the headline (skrót, wyjaśnienie) is filled in last.
- **Section [Rozpoczęcie pisania](pl/GRIM.md)** — workflow for drafting sessions bottom-up (hard-to-recall details and specifics before summaries), with a worked `^^` example using `APP:`.
- **Recycle marker `♻`** in the strikethrough header example: marks a scene that was not used and should be repurposed elsewhere.

### Changed

- **Manifest** in `pl/GRIM.md` bumped to **v0.9**.
- **`^` modifier** renamed from *przypis* to *uzupełnienie po sesji*; meaning and examples updated to match post-session completion.
- **Prose readability pass** across the Polish manifest (~140 lines touched):
  - Instructional paragraphs rewritten from telegraphic, em-dash-heavy style into full sentences with explicit connectors (`gdy`, `ponieważ`, `np.`, `czyli`, colons).
  - Orphan sentence fragments given an explicit subject (e.g. *Wzrok zatrzymuje się, gdy…*).
  - Layer and subblock intros reframed as complete definitions instead of sentence stubs.
  - Modifier table *Znaczenie* column clarified where `—` had acted as a pseudo-connector.
  - Step-by-step examples (*Krok 1–7*) unified to use colons and causal phrasing.
- **Terminology** (`BG`, `MG`, `BN`): definitions now use *czyli* instead of em-dash apposition.
- **Block-mode guidance** (layout under skrót, subsections, `&` under headers): expanded for scanability without changing rules.
- **Wyjaśnienie layer intro:** *bez nawiasów* corrected to *bez pogrubienia*, contrasting plain text with the bold skrót; the layer may still use GRIM symbols (`<>`, `{}`, `//`, etc.).

### Unchanged on purpose

- Title `# GRIM — Glance, Read If Missing`, section headers (`### REL: — relacje`), GRIM notation inside code fences, and in-fiction quotes still use `—` where appropriate.

## Changes for v0.8

### Changed

- **Manifest** in `pl/GRIM.md` bumped to **v0.8**.
- **Subblock tags must be uppercase** (e.g. `REL:`, `APP:`, `RP:`; not `rel:`, `app:`, `rp:`). Documented and exemplified throughout the Polish GRIM specification (`pl/GRIM.md`).
- **`//!` (surface falsehood) layer:** reframed as **nieprawdę** (not “lie” phrasing); added guidance to prefer hedged wording (“wydaje się”, “wygląda na”) over flat assertion.
- **Polish spec (`pl/GRIM.md`) — clarity and examples**
  - **Secrets (`//`) intro:** duplicate paragraph about multiple secrets and block mode removed.
  - Default *active* entity wording tightened (significance in play stated up front).
  - Strikethrough section: small wording polish; task vs. strike contrast now uses *zakończone* for completed checklist items.
  - Task/checklist examples: mechanics phrasing and item order in the sample block adjusted.
  - **Progression:** example for striking unused steps now keeps the step number outside the strike: `2. ~~!! Kapitan przybywa~~`.
  - **Entity-symbol headers:** introductory prose shortened; markdown sample shows a regional category with body text, Polish place names, and nested `####` headings for sub-locations and a character under the same region.
- **Optional header emoji** section: prose revised (default is still "no emoji" unless type or scan speed benefits).

### Removed

- **`📝` entity-type emoji** for quests/tasks; tasks are represented only with markdown task markers `- [ ]` / `- [x]`. Removed from the entity emoji table and the emoji index in `pl/GRIM.md`.
