🇬🇧 **[English](./README.md)** | 🇵🇱 Polski ✔

# GRIM — Glance, Read If Missing

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?label="Licencja")](https://creativecommons.org/licenses/by/4.0) ![Status](https://img.shields.io/badge/status-pre--release-yellow?label="Status") ![Wersja](https://img.shields.io/github/v/tag/dudematthew/grim-notation?sort=semver&label=Wersja)

**GRIM** to minimalistyczny system notacji dla Mistrzów Gry. Zamiast organizować informacje jak dokument — organizuje je jak decyzję: im dalej w prawo, tym rzadziej potrzebne.

```
👤 **Borgrim**+ <w kuźni po zmroku> kowal, wie o tunelu za karczmą {Persw DC12} // szantażowany przez Gildię
```

Wzrok skanuje od lewej i zatrzymuje się gdy ma wystarczająco. Najczęściej — na pogrubionym skrócie.

---

## Co to jest

GRIM to lekki język operacyjny do prowadzenia sesji RPG — zbudowany na Markdown, zaprojektowany pod percepcję MG przy stole. Minimalizuje czas od spojrzenia do wdrożenia, maksymalizuje ilość znaczenia w jednej linii.

→ **[Pełny manifest: GRIM.md](./pl/GRIM.md)**

---

## Szybki start

Każda encja dzieli się na warstwy od lewej do prawej:

| Warstwa | Symbol | Przykład |
|---|---|---|
| Symbol typu | `👤` `🔎` `!!` | `👤` = postać |
| Skrót myślowy | `**tekst**` | `**Borgrim**+` |
| Wyjaśnienie | tekst | `kowal, wie o tunelu` |
| Kontekst | `<tekst>` | `<w kuźni po zmroku>` |
| Mechanika | `{tekst}` | `{Persw DC12}` |
| Sekret | `// tekst` | `// szantażowany` |

Tryb liniowy dla prostych encji, blokowy gdy ich złożoność rośnie:

```markdown
👤 **Borgrim**+
kowal, wie o tunelu za karczmą
- <w kuźni po zmroku> {Persw DC12 | DC18 -> mówi o kontrakcie}
- // szantażowany od trzech miesięcy

rel:
  - **Thordin**+ brat
  - 🏛️ **Gildia Cieni**- szantażysta

! pytają o kontrakt -> panikuje, zaprzecza, wychodzi
```

→ **[Cheatsheet](cheatsheet/)** · **[Przykłady](examples/)**

---

## Zawartość repo

```
grim-rpg/
├── GRIM.md            ← pełny manifest systemu
├── cheatsheet/        ← skrócona wersja do druku
└── examples/          ← gotowe przykłady sesji, NPC, lokacji
```

---

## Licencja

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — możesz używać, adaptować i dystrybuować, pod warunkiem uznania autorstwa.

*GRIM autorstwa [dudematthew](https://github.com/dudematthew)*