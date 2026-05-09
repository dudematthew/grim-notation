🇬🇧 English ✔ | **🇵🇱 [Polski](./README.pl.md)**

# GRIM — Glance, Read If Missing

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?label="License")](https://creativecommons.org/licenses/by/4.0) ![Status](https://img.shields.io/badge/status-pre--release-yellow?label="Status") ![Wersja](https://img.shields.io/github/v/tag/dudematthew/grim-notation?sort=semver&label=Version)

---

**GRIM** is a minimal notation system for Game Masters. Instead of organizing information like a document — it organizes it like a decision: the further right, the less often you need it.

```
👤 **Borgrim**+ <at the forge after dark> blacksmith, knows about the tunnel {Persuasion DC12} // blackmailed by the Guild
```

Your eye scans left to right and stops when it has enough. Usually — at the bold shorthand.

> ⚠️ **The full system is currently available in Polish only.** English translation is planned for v1.0.
> In the meantime, the notation itself is largely language-agnostic — symbols, structure and examples are readable without fluent Polish.

→ **[Full manifest: pl/GRIM.md](pl/GRIM.md)**

---

## What it is

GRIM is a lightweight operational language for running RPG sessions — built on Markdown, designed for GM perception at the table. It minimizes time from glance to implementation, maximizes meaning per line.

---

## How it works

Every entry is split into layers, left to right:

| Layer | Symbol | Example |
|---|---|---|
| Type symbol | `👤` `🔎` `!!` | `👤` = character |
| Shorthand | `**text**` | `**Borgrim**+` |
| Explanation | plain text | `blacksmith, knows about the tunnel` |
| Context | `<text>` | `<at the forge after dark>` |
| Mechanics | `{text}` | `{Persuasion DC12}` |
| Secret | `// text` | `// blackmailed` |

Inline mode for simple entries, block mode when complexity grows:

```markdown
👤 **Borgrim**+
blacksmith, knows about the tunnel behind the inn
- <at the forge after dark> {Persuasion DC12 | DC18 -> talks about the contract}
- // blackmailed for three months

rel:
  - **Thordin**+ brother
  - 🏛️ **Shadow Guild**- blackmailer

! they ask about the contract -> panics, denies, leaves
```

---

## Repo structure

```
grim-rpg/
├── README.md            ← you are here (English)
├── README.pl.md         ← Polish
├── en/
│   ├── GRIM.md          ← full manifest (translation in progress)
│   ├── examples/
│   └── cheatsheet/
└── pl/
    ├── GRIM.md          ← full manifest (current)
    ├── examples/
    └── cheatsheet/
```

---

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — free to use, adapt and distribute with attribution.

*GRIM by [dudematthew](https://github.com/dudematthew)*