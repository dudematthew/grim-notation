# GRIM — Glance, Read If Missing
---
## Manifest v0.8
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg?label="Licencja")](https://creativecommons.org/licenses/by/4.0)


![GRIM](https://i.imgur.com/MEn2OCI.png)

**GRIM** to minimalistyczny system notatek dla RPG. Został stworzony aby ułatwić tworzenie i zarządzanie notatkami w trakcie sesji przez MG.

<!--
[TOC]
-->

## Filozofia

GRIM jest zbudowany na założeniu, że przed oczami MG jest zawsze tylko najprostsza możliwa wersja informacji.
Wzrok skanuje **skróty myślowe** — skompresowane frazy, które przywołują zakodowaną wiedzę. Tylko jeśli skrót myślowy wystarcza, czytasz dalej. Jeśli nie — sięgasz po rozwinięcie. W ten sposób czytanie notatek jest szybkie i skuteczne. Jeśli znamy 80% sesji, nie musimy czytać wszystkiego jeszcze raz żeby przypomnieć sobie 20%.

## Dlaczego GRIM?

GRIM powstał z potrzeby odejścia od klasycznego "notatnika MG", który organizuje informacje głównie przez hierarchię dokumentu (nagłówki, sekcje, podsekcje), ale nie pomaga w szybkim rozumieniu sytuacji przy stole. W tradycyjnym podejściu łatwo znaleźć informację, ale trudno ją natychmiast ułożyć sobie w głowie — trzeba ją czytać, interpretować i dopiero przekształcać w decyzję narracyjną.

GRIM odwraca ten proces: zamiast priorytetyzować strukturę dokumentu, priorytetyzuje **percepcję MG w czasie rzeczywistym**. Informacja nie jest tu tylko opisana — jest od razu zakodowana w formie, która sugeruje jej użycie: kontekst (`<>`), przyczynowość (`->`), warunkowość, efekt, sekret czy relację. Dzięki temu notatki nie wymagają "czytania w pełni", tylko skanowania i natychmiastowego rozpoznania znaczenia.

Nagłówki przestają być encyklopedycznym podziałem treści, a stają się narzędziem nawigacji po stanie świata i scenach. Sama treść GRIM może jednocześnie opisywać obiekt, regułę, zdarzenie lub potencjalną zmianę stanu — bez potrzeby przenoszenia informacji między różnymi formatami. To redukuje przełączanie kontekstu i pozwala MG utrzymać "ciągłość wyobrażenia" zamiast ciągłego przeskakiwania między interpretacją a strukturą.

W efekcie GRIM nie jest systemem notatek w klasycznym sensie, tylko lekkim językiem operacyjnym do prowadzenia sesji RPG: minimalizuje czas od spojrzenia do decyzji, a maksymalizuje ilość znaczenia zawartego w jednej linii tekstu.

## Terminologia

Skrót **BG** znaczy *Bohater Gracza* — są to postacie prowadzone przez graczy przy stole.
Skrót **MG** znaczy *Mistrz Gry* — prowadzący sesję.
Skrót **BN** znaczy *Non-Player Character* — są to postacie fikcyjne, niezależne od graczy.

## Markdown a GRIM
GRIM jest zbudowany na [Markdown](https://wikipedia.org/wiki/Markdown) — języku opisu tekstu używanego do organizowania informacji. Markdown daje gotową infrastrukturę: nagłówki, listy, tabele, pogrubienia, cytaty. GRIM nie wymyśla własnego formatu — nakierunkowuje tę składnię tak, żeby służyła nie strukturze dokumentu, ale **percepcji MG przy stole**.

W klasycznym użyciu nagłówki mówią *gdzie szukać*. W GRIM mówią *co jest teraz ważne*. Najważniejsze informacje trafiają najwyżej w hierarchii. Wzrok skanuje w odpowiedniej kolejności i odnajduje najważniejsze informacje szybciej i skuteczniej.

## Anatomia linii

Sercem GRIMa jest zapisywanie informacji w liniach tekstu, zwanych encjami. Encja opisuje jeden byt — postać, miejsce, przedmiot, trop czy zdarzenie. Każda encja dzieli się na warstwy ułożone od lewej do prawej według jednej zasady: im dalej w prawo, tym rzadziej potrzebna.

| Symbol | Skrót myślowy | Wyjaśnienie | Kontekst | Mechanika | Sekret |
|---|---|---|---|---|---|
| 🔎 | **Świeże ślady** | Wóz na drodze pozostawił ślady | <przy wjeździe do wioski> | {Spostrz. DC10} | // bandyci wiozą jeńców do magazynu |

Przykład powyższej encji pisany byłby tak:

```markdown
🔎 **Świeże ślady** wozu na drodze <przy wjeździe do wioski> {Spostrz. DC10} // bandyci wiozą jeńców do magazynu
```

Wzrok skanuje linię od lewej i zatrzymuje się gdy ma wystarczająco informacji by zidentyfikować encję. Symbol mówi czym jest encja zanim przeczytasz jej nazwę. Skrót myślowy przywołuje pełny obraz w jednym słowie lub frazie. Jeśli to nie wystarczy, czytasz wyjaśnienie — ale często nie musisz. Kontekst, mechanika i sekret są dostępne gdy wzrok po nie sięgnie, nie wcześniej.

Ten porządek nie jest przypadkowy: warstwy bliżej lewej brzmią ogólniej i dotyczą identyfikacji. Warstwy bliżej prawej brzmią szczegółowiej i dotyczą użycia. MG który zna encję zatrzymuje się przy skrócie. MG który jej nie pamięta — czyta dalej.

### Warstwy

| Element | Symbol | Typ informacji |
|---|---|---|
| Symbol | `👤` `🔎` `!!` | Typ encji lub rola informacji. Nakreśla właściwość przed przeczytaniem nazwy. |
| Skrót myślowy | `**tekst**` | Skrócony opis — w jednym słowie lub frazie. Zapisany czysto, bez symboli. |
| Wyjaśnienie | tekst | Rozwinięcie skrótu — czytane gdy skrót nie wystarcza. Rozwijany przez inne warstwy. |
| Kontekst | `<tekst>` | Stan sceny obowiązujący w tle. Dotyczy tego co stoi bezpośrednio po nim. |
| Mechanika | `{tekst}` | Jak encja działa mechanicznie — matematyka, statystyki, efekty, rzuty. |
| Sekret | `// tekst` | Ukryta prawda znana początkowo tylko MG. Zawsze na końcu linii. |
| Fałsz | `//! tekst` | Pozorna prawda formułowana tak jak gracze ją odbiorą. |
| Głęboka warstwa | `[tekst]` | Opcjonalne tło — lore, historia, odnośniki. Nie wymagane do odkrycia przy stole. |
| Cytat | ``` `cytat` ``` | Bezpośrednia treść obecna w świecie. Zazwyczaj wprost wypowiadana w kontekście encji. |

#### Symbol

Stoi na początku linii, zawsze przed skrótem myślowym i nigdy po nim. Jego obecność jest opcjonalna — większość linii zaczyna się bez symbolu. Gdy go używamy, ma jedno z trzech znaczeń:

- **Typ encji** — identyfikuje czym jest encja zanim przeczytasz jej nazwę. `👤 **Borgrim**` — wzrok widzi że to postać o imieniu Borgrim.
- **Emoji-rola** — nakreśla rolę informacji w grze, nie typ encji. Przykładowo `🔎` sygnalizuje trop dostępny dla graczy do znalezienia. Pełną listę zawiera sekcja [Emoji jako kompresja treści](#emoji-jako-kompresja-treści).
- **Modyfikator** — nakreśla właściwość encji przed przeczytaniem. Przykładowo `??` oznacza że MG nie jest pewien wykorzystania encji, `!!` że encja jest krytyczna dla sesji. Pełną listę modyfikatorów można znaleźć w sekcji [Modyfikatory](#modyfikatory).

Symbole można łączyć w odpowiedniej kolejności - sprawdź sekcję [Łączenie symboli](#łączenie-symboli).


#### Skrót myślowy

Serce systemu — pogrubiona, skompresowana wersja encji w jednym słowie lub krótkiej frazie, która przywołuje pełny obraz. Jeśli skrót wystarcza, reszty linii nie trzeba czytać.

Skrót powinien od razu zawierać kontekst całej encji: `**złodziej nocny**` zamiast `**złodziej**`. Jest zawsze czysty — bez specjalnych symboli, warunków i strzałek: `**złodziej nocny**` zamiast `**złodziej <w nocy>**`. Warunkowość sugerujemy słowami.

#### Wyjaśnienie

Znajduje się bezpośrednio po skrócie — czysty tekst, bez nawiasów. To pierwsza i najczęściej czytana warstwa rozwinięcia. W wyjaśnieniu można używać symboli warunków, modyfikatorów i sekretów.

#### Kontekst

Stoi bezpośrednio przed tym czego dotyczy — przed wyjaśnieniem, mechaniką lub subblokiem. Nigdy przed skrótem myślowym. Jeden kontekst dotyczy jednej informacji — nie piszemy serii `<><>` na jednej linii, tylko łączymy warunki wewnątrz jednego nawiasu: `<w kuźni & po zmroku>`.

```markdown
<w kuźni po zmroku> kowal, mówi o tunelu {Persw DC12}
<straż pijana || strażnik śpi> -> można przejść bez testu
```

#### Mechanika

Opis mechaniki gry mający znaczenie dla encji: matematyka, statystyki, efekty, rzuty. Trafia w nawiasy klamrowe. 

```markdown
🔎 **Świeże ślady** wóz na drodze <przy wjeździe> {Spostrz DC10}
👤 **Borgrim**+ kowal {Persw DC12 | DC18 -> mówi o kontrakcie}
```

#### Sekret

Ukryta prawda znana tylko MG — co naprawdę się dzieje za fasadą którą widzą gracze. Trafia po `//` i zawsze stoi na końcu linii. Jeśli encja ma wiele sekretów, przechodzimy do trybu blokowego — przy dwóch lub więcej `//` linia staje się nieczytelna.

#### Fałsz

Pozorna prawda formułowana tak jak gracze ją odbiorą — jako twierdzenie, nie opis. Trafia po `//!` i opisuje **nieprawdę** — formułowaną tak jak BN by ją wypowiedział lub jak gracze ją odbiorą. Dobrze zapisywać ją w formie przypuszczającej, np. "wydaje się" lub "wygląda na" zamiast "jest".
Para występuje często razem: `//!` opisuje co gracze mają sądzić, `//` opisuje prawdę pod spodem.

```markdown
//! Cera wydaje się być właścicielką magazynu, oferuje 50 srebrnych za pomoc
// przejęła magazyn siłą, prawdziwy właściciel związany w piwnicy
// zapłaci o wiele mniej niż oferuje
```

#### Głęboka warstwa

Opcjonalne tło dla MG — lore, historia świata, motywacje, odnośniki. Trafia w nawiasy kwadratowe. Różni się od `//` intencją: `[...]` to kontekst który *można* ujawnić graczom, `//` to dane których gracze początkowo nie znają.

```markdown
[tunel zbudowany 200 lat temu przez krasnoludy z Klanu Vossa]   ← lore, do stopniowego ujawnienia
// Gildia go szantażuje                                          ← sekret odkrywany w grze
```

Jeśli coś musi być przeczytane w grze, nie należy do `[...]`.

#### Cytat

Kiedy reakcja postaci jest oczywista i dosłowna, szybciej ją zacytować niż opisywać. Cytat trafia w backtiki i może zastąpić wyjaśnienie albo uzupełnić je o konkretną frazę.

```markdown
**Borgrim- odrzuca gości** `Wynoście się z mojej chaty!` // boi się że wiedzą za dużo
👤 **Strażnik**+ przyjazny, pyta o cel podróży `Skąd jedziecie, dobrzy ludzie?`
```

Backtiki sygnalizują że to treść istniejąca w świecie gry — słowa które padają, nie opis tego co postać robi. Dłuższe wypowiedzi i pełne sceny dialogowe trafiają do bloku `📢` — cytat w linii jest dla krótkich, gotowych do wypowiedzenia fraz.

#### Kontekst a zdarzenia

`<>` opisuje **kontekst sceny** — coś co *trwa* w tle i zmienia interpretację tego co się dzieje: pora dnia, nastrój tłumu, pozycja straży. Kontekst nie jest zdarzeniem — nie jest punktem w czasie, tylko stanem części encji.

Zdarzenia to to co się *dzieje* — działanie, reakcja, zmiana. Zapisujemy je bez nawiasów, bezpośrednio w tekście. Strzałki (`->`, `-->`, `<--`, `<<<`) łączą jedno z drugim: stan może warunkować zdarzenie, a zdarzenie może zmieniać stan.

```markdown
<w nocy> wróżka tańczy w świetle księżyca
<straż pijana> -> nie reaguje na hałas
wybucha pożar -> chaos na molo --> straż wraca o świcie
```

---

### Dwa tryby zapisu

#### Tryb liniowy

Omawiany do tej pory tryb zapisu w jednej linii używamy dla prostych encji. Taka linia zawiera tylko jedną encję i wszystkie jej warstwy. Większość notatek sesyjnych to pojedyncze fakty, tropy i obserwacje.

```markdown
👤 **Borgrim**+ kowal, wie o tunelu za karczmą <w kuźni> {Persw DC12} // szantażowany
🔎 **Świeże ślady** wozu na drodze <przy wjeździe> {Spostrz DC10} // wiozą jeńców
!! Kapitan zna twarze BG [listy gończe z Port Veth]
**Sterta skrzynek** w rogu sali — zamknięte na kłódkę {Zrę DC14}
```

#### Tryb blokowy

Tryb liniowy przestaje wystarczyć gdy encja ma więcej niż jeden sekret, kilka wyzwalaczy z różnymi skutkami albo relacje które mają znaczenie przy stole. Wciśnięcie tego wszystkiego w jedną linię nie przyspiesza skanowania — utrudnia je. Wtedy skrót myślowy staje się nagłówkiem bloku, a warstwy rozkładają się na osobne linie pod nim.

Zagnieżdżenie tworzymy przez wcięcia list markdown — każdy poziom `-` głębiej to kolejna warstwa podrzędna. Można je zagnieżdżać dowolnie głęboko, stosując standardowe wcięcia:

```markdown
- pierwszy poziom
  - drugi poziom
    - trzeci poziom
```

Wyjaśnienie piszemy bezpośrednio pod skrótem, na tym samym poziomie wcięcia. Jeśli to jeden ciągły opis — piszemy akapit bez `-`. Gdy kolejne linie to różne warstwy GRIM — osobno `//`, `<>`, `{}`, `!` — otwieramy listę `-`. Mechanika i statystyki trafiają na dół bloku, po warstwach narracyjnych: czytelnik najpierw rozumie kogo i co dotyczy encja, dopiero potem sięga po liczby. W trybie blokowym wzrok skanuje w obu osiach — w prawo po treść warstwy, w dół po kolejne warstwy. Zatrzymuje się gdy ma wystarczająco, pomijając resztę bloku.

Każdy blok i podblok zaczyna się skrótem myślowym podsumowującym jego treść. `**Mieszkańcy**` to etykieta — wzrok zatrzymuje się i czeka na kontekst. `***Mieszkańcy przeczą Cerze***` to skrót myślowy subsekcji — wzrok zna już treść i może podblok pominąć. Reguła obowiązuje na każdym poziomie zagnieżdżenia.

```markdown
👤 **Borgrim**+
kowal, wie o tunelu za karczmą
- <w kuźni po zmroku> {Persw DC12 | DC18} -> mówi o kontrakcie
- // szantażowany przez Gildię od trzech miesięcy
- REL:
  - **Thordin**+ brat [Thordin odkrył tunel jako pierwszy]
  - **Anata** znajoma ze sklepu na rogu <na ulicy> sprzeda mu jabłka za 2 md

***Alkohol w szafce***
Trzyma w szafce 80-letnią wódkę
- <gracze go nie nękają> 
  - proponuje im kieliszek
  - opowiada o Thordinie

! pytają o kontrakt
- -> panikuje, zaprzecza --> zmusza do opuszczenia kuźni
- // rozważał zerwanie <<< może pomóc graczom
```

Subsekcje — jak `***Alkohol w szafce***` czy `! pytają o kontrakt` — działają dokładnie jak blok główny: mogą mieć własny skrót, wyjaśnienie i zagnieżdżone warstwy. Skróty myślowe subsekcji oznaczamy pogrubieniem i kursywą `***tekst***` — odróżnia je to wizualnie od skrótu głównego bloku i pozwala wzrokowi od razu rozpoznać poziom zagnieżdżenia. Te same zasady obowiązują na każdym poziomie. Wyzwalacz `!` z jednym skutkiem można zapisać w jednej linii: `! pytają o kontrakt -> panikuje`. Jeśli skutków jest więcej, wyzwalacz otwiera własną sub-listę. Kolejną encję oddzielamy pustą linią.

#### Wybór trybu

| Sytuacja | Tryb |
|---|---|
| Encja z jednym lub dwoma faktami | liniowy |
| Encja z kilkoma triggerami lub sekretami | blokowy |
| Wiele notatek `//` w jednej encji | blokowy |
| Notatka pisana w trakcie sesji | zwykle liniowy; przy wielu wyzwalaczach `!`, kilku `//` lub wielu warstwach w jednym miejscu rozszerzamy do blokowego |

#### Otwarte znaczniki

W trybie blokowym możemy używać otwartych wersji znaczników, które nie wymagają domknięcia. Otwarty znacznik dotyczy wtedy całej linii do jej końca. Zamiast `[tekst]` piszemy `[[ tekst`, zamiast `<kontekst>` piszemy `<< kontekst`, zamiast `{mechanika}` piszemy `{{ mechanika`.

Robimy to w blokach, ponieważ tam każda warstwa zwykle zajmuje osobną linię i podwójny znak otwarcia jednoznacznie sygnalizuje, że dana warstwa rozciąga się do końca tej linii. W trybie liniowym znaczniki muszą się zamykać, bo na jednej linii mieści się wiele warstw obok siebie.

```markdown
**Riord**- 
Były pirat, szantażowany przez Gildię
- [[ kocha córkę ponad wszystko, przy jej imieniu pęka natychmiast
- << tylko sam na sam, po zmroku
- {{ Wgląd DC10 widać strach | DC14 widać kłamstwo
- // wie że ładunek to ludzie, boi się mówić
- //! wygląda na lojalnego
```

*Uwaga dla użytkowników edytora Obsidian: Aby otwarte znaczniki `[[` nie rozpoczynały linku, musimy użyć spacji przed tekstem. Na przykład `[[ coś` zamiast `[[coś`.*

#### Odnośniki aplikacji

[Obsidian](https://obsidian.md/), [Notion](https://www.notion.so/), [Kanka](https://kanka.io/) i podobne narzędzia oferują wbudowane typy odnośników do encji. Korzystanie z nich jest opcjonalne, ale warto robić to konsekwentnie.

Odnośnik zastępuje lub otacza nazwę w skrócie myślowym — dokładnie w tym samym miejscu co bold. Pogrubienie obejmuje cały odnośnik razem z jego składnią.

```markdown
👤 **[[Borgrim]]**+               ← Obsidian (wikilink)
👤 **@Borgrim**+                  ← Notion / Kanka (mention)
```

W wyjaśnieniach i relacjach, gdzie encja jest już znana i nie otwieramy nowego bloku, stosujemy sam odnośnik bez pogrubienia:

```markdown
REL:
  - [[Thordin]]+ brat
  - @Szet-
```

W przypadkach w których pojawiają się zewnętrzne encje, możemy użyć odnośnika do nich w wyjaśnieniu.

```
  [emoji-typ]  **Napad na magazyn**  Po zmroku [[Bernard]]- i [[Szet]]- wchodzą we dwoje do magazynu //! [[Gregory]] czeka na nich z pułapką
```

---

## Modyfikatory

Modyfikatory to znaki które standaryzują często powtarzane sytuacje. Zamiast pisać "jeśli gracze pójdą do kowala, to..." piszemy `! idą do kowala -> ...`. Pojedynczy znak zastępuje całą frazę i pozwala wzrokowi natychmiast rozpoznać typ informacji.

| Znak | Rola | Znaczenie | Przykład |
|---|---|---|---|
| `!` | wyzwalacz akcji graczy | Otwiera linię informacji która ma znaczenie tylko gdy gracze coś zrobią. Czyta się jako "jeśli gracze...". Można łączyć z `->` w jednej linii. | `! pytają o kontrakt -> panikuje` |
| `!!` | informacja krytyczna | Coś, czego nie można zapomnieć ani pomylić przy stole. Używamy oszczędnie — nadużywany znak traci wagę. | `!! Kapitan zna ich twarze` |
| `!?` | rewelacja / zwrot akcji | Stoi przed informacją, która gdy wyjdzie na jaw, odwraca scenę, relację lub całą historię. Oznacza fakt, nie zdarzenie odkrycia — nie używamy w czasie przeszłym. | `!? Borgrim to informator Gildii` |
| `->` | następstwo / skutek | Konsekwencja w obrębie tej samej sceny. `X -> Y` opisuje łańcuch zdarzeń. `<X> -> Y` opisuje skutek oparty o **stan sceny** (kontekst): w stanie `<X>` zachodzi `Y`. | `<po zmroku> -> zamyka kuźnię` |
| `-->` | skutek odroczony w czasie | Konsekwencja która zadziała później — wymaga jawnego określenia kiedy (np. "później", "za godzinę", "następnego dnia"). Bez podanego czasu używamy `->`. | `BG odpuszczają --> następnego dnia Cera zabija Jimsa` |
| `<<<` | zapowiedź / foreshadowing | Odwrócona strzałka skutku — aktualna encja lub fakt wynikający lub zapowiadający przyszłe wydarzenia. Czytamy jako "to, co tu widzimy, jest zapowiedzią tego wydarzenia". MG zaznacza punkt połączenia między sceną a czymś, co się pojawi. | `// krostki na ręce <<< wielka pandemia` |
| `<--` | poprzedniczka | Informacja wynikająca lub zapowiadająca przyszłe wydarzenia, ale nie wymaga jawnego śledzenia w tej scenie. Kontekst istnieje, jednak raczej jako informacja dla MG. | `zachowuje się podejrzanie <-- Gildia go szantażuje od miesięcy` |
| `\|\|` | alternatywa | Jedno albo drugie, MG wybiera przy stole w zależności od sytuacji. Łączy też warunki: `<A \|\| B>`. *Tabele ulegają uszkodzeniu przy używaniu `\|`, dlatego używamy `\\|\\|`.* | `ucieka || negocjuje` |
| `&` | i też | Łączy informacje równorzędne na jednej linii bez sugerowania relacji. Łączy też warunki: `<A & B>`. | `kowal & wie o tunelu` |
| `+` / `-` | nastawienie BN do graczy | Bez spacji po imieniu określa stosunek encji do bohaterów graczy. Brak oznaczenia oznacza neutralność lub stosunek czysto transakcyjny. | `**Borgrim**+`, `**Szet**-` |
| `+` / `-` (między encjami) | relacja dwustronna | Ze spacjami z obu stron łączy dwie encje. `+` oznacza sojusz, sympatię, współpracę. `-` oznacza wrogość, rywalizację, konflikt. Działa dla BN, frakcji, miejsc, organizacji. | `Stink Fists + Wioska`, `Stink Fists - Pissdrinkerzy` |
| `~` | przybliżenie | Wartość orientacyjna lub niepewna. | `~3 dni`, `~połowa sali` |
| `??` | niepewność | MG nie jest pewien — niespójność fabularna, dziura w logice, coś do sprawdzenia po sesji. | `// ?? planował ucieczkę` |
| `^` | przypis | Element do dopracowania lub uzupełnienia po sesji. | `{Persw DC12} ^` |

### Złożone konteksty

Gdy informacja zależy od więcej niż jednego elementu **stanu sceny**, możemy łączyć je w obrębie jednego `<>` używając `&` (oba aktywne równolegle) lub `||` (wystarczy jeden). Dowolna kombinacja pisana naturalnym językiem wewnątrz `<>` też jest dopuszczalna.

```markdown
<w kuźni & po zmroku> {Persw DC12}
<PC mają broń || straż jest pijana> -> ucieka
<sam na sam & po zmroku> -> przyznaje się
```

Nie tworzymy serii oddzielnych `<><>` na jednej linii. Konteksty należące do tej samej informacji łączymy w jeden nawias.

Wieloma **kontekstami** (`<>`) z różnymi skutkami nie obciążamy jednej linii. Linia w stylu `<X> -> Y; <Z> -> W` jest nieczytelna — rozbijamy ją na sub-punkty pod wspólnym skrótem myślowym.

### Zapis pod nagłówkiem

Zasada ogólna: `&` łączy fragmenty na tej samej linii — dwa krótkie fakty tej samej natury, na przykład oba w wyjaśnieniu. Nie zastępuje punktora: `- & coś` to zwykły punkt listy którego treść zaczyna się od `&`, co jest mylące przy czytaniu. Jeśli coś jest osobnym punktem, zapisujemy go normalnie bez `&` na początku.

W trybie liniowym gdy wszystkie warstwy mieszczą się czytelnie, jedna linia jest najszybsza do czytania. Dwa równorzędne detale w wyjaśnieniu można połączyć przez `&`: `udaje kowala & wie o tunelu`.

W trybie blokowym mamy trzy poziomy zapisu pod nagłówkiem, wybierane według tego ile warstw GRIM zawiera dana informacja:

- **Akapit** — gdy pod skrótem myślowym następuje jeden ciągły opis, który czyta się razem jako całość. Nie rozdzielamy go na punkty bo nie ma potrzeby pomijać żadnej jego części osobno.

- **Lista** — gdy kolejne linie pełnią różne role w notacji: osobno `//!`, osobno `//`, osobno `{}`, osobno `<>`. Lista pozwala wzrokowi pomijać wybrane punkty bez czytania sąsiednich.

- **`&` wewnątrz punktu listy** — dopuszczalne gdy oba fragmenty są tego samego rodzaju i mieszczą się w jednej linii. Na przykład `- //! wydaje się być szczery & udaje kowala` jest poprawne jeśli obie części to warstwa fałszu graczy. Gdy jedna część to fałsz a druga mechanika, rozdzielamy na dwa osobne punkty.

```markdown
**Goblin na trakcie**
gobliński podróżny, sprzedaje ser za 2 md [normalny koszt sera 3 md]
- //! jego ser wygląda na świeży
- // ser powoduje chorobę {oszołomienie DC12}
- {perswazja z utrudnieniem -> mówi o maruderach}
```

---

## Subbloki

Subblok to nazwana lista wewnątrz bloku, która organizuje określony typ zawartości dotyczącej encji nadrzędnej. Każdy subblok otwiera się tagiem zakończonym dwukropkiem — **tag zapisujemy drukowanymi literami** (np. `REL:`, `APP:`, `RP:`, a nie `rel:`, `app:`, `rp:`). Nie jest pogrubiony ani pisany kursywą, ponieważ nie jest to skrót myślowy. Zawartość zapisujemy od najistotniejszego elementu do najbardziej pomijal­nego — czytelnik może przerwać skanowanie w dowolnym miejscu nie pomijając najważniejszych szczegółów. Każda linia to jeden element — stosujemy do nich te same warstwy GRIM co do reszty bloku.

Możesz tworzyć własne subbloki — wystarczy dodać wyjaśnienie po `//`, żeby czytelnik wiedział, co tag oznacza:

```markdown
CHOICES: // wybory do podjęcia
LOOT: // co można zabrać
```

---

### `REL:` — relacje

Powiązania encji z innymi encjami fikcyjnymi: BN, frakcjami, miejscami, organizacjami. Otwieramy `REL:` tylko wtedy, gdy relacja ma znaczenie przy stole — wpływa na decyzje, otwiera wątki, generuje konflikty lub jest istotna dla przedstawienia encji. Relacje będące częścią tła, bez wpływu na rozgrywkę, pomijamy.

Pierwsza linia to relacja, która najszybciej zmieni cokolwiek przy stole. Jeśli encja ma tylko jedną relację, zapisujemy ją liniowo w wyjaśnieniu zamiast otwierać subblok.

```markdown
👤 **Rhianna**+
botanistka, pogodna, nieświadoma obsesji którą wzbudza
- //! wydaje się być wiedźmą <<< oskarżana o czary

REL:
  - **Bailey**+ obsesja jednostronna — może działać pochopnie w jej obronie
  - 🏛️ **Cech Zielarzy**- wyrzucona za "niesubordynację"
  - **Lanja**+ siostry, absolutna lojalność
  - **Szet**- złośliwy, kłamie
```

---

### `APP:` — wygląd

Charakterystyczne cechy wyglądu, które skupiają wzrok i zostają w pamięci. Pierwsza linia to detal najczęściej wymieniany lub najtrudniejszy do przeoczenia — to, co gracz zobaczy i zapamięta.

```markdown
👤 **Mira**-
handlarka mapami, zna każdy szlak w prowincji

APP:
  - brakuje lewego ucha
  - zielony płaszcz z dziesiątkami kieszeni, zawsze coś z nich wystaje
  - mówi bez przerwy, rzadko patrzy w oczy rozmówcy
```

---

### `RP:` — odgrywanie

Charakterystyczne zachowania do naśladowania przy stole. Pierwsza linia to sygnał, który najszybciej da graczom znać, że MG właśnie *jest* tą postacią — gest, manieryzm, fraza. Kolejne to szczegóły dokładające głębi.

```markdown
👤 **Borgrim**+
kowal, wie o tunelu za karczmą

RP:
  - przed odpowiedzią zawsze uderza młotem w kowadło - raz, z namysłem
  - mówi powoli, urwanymi zdaniami, jakby każde słowo kosztowało
  - <przy pytaniach o Gildię> porządkuje narzędzia zamiast patrzeć na BG
```

---

### Inne standardowe subbloki

`KNOW:` — lista rzeczy, które encja wie i może ujawnić, od tej o największej wartości fabularnej. Przydatne gdy BN jest źródłem informacji i chcemy wiedzieć, co "wyciągniemy" zależnie od podejścia.

`INV:` — przedmioty przy sobie lub w zasięgu, od najbardziej istotnego dla rozgrywki. Stosujemy gdy zawartość kieszeni BN może wejść do gry — jako loot, dowód, narzędzie negocjacji.

```markdown
👤 **Mira**-
handlarka mapami, zna każdy szlak w prowincji

KNOW:
  - zna obóz Pissdrinkerów — była tam trzy dni temu
  - ?? wie że most na Skarze jest zniszczony
    - // słyszała od kupca, sama nie sprawdzała 
    - handluje od piętnastu lat, zna każdego strażnika na szlaku

INV:
  - mapa z zaznaczonym obozem (żąda 20 md)
  - klucz - nie wie co otwiera, znalazła przy drodze // otwiera skład w Portven
  - nóż ukryty w bucie
```

---

Subbloki można łączyć w jednym bloku w kolejności zależnej od priorytetu. Porządek między subblokami sugeruje priorytet — najpierw to, czego MG najprawdopodobniej będzie szukać w tej scenie:

```markdown
👤 **Borgrim**+
kowal, wie o tunelu za karczmą
- // szantażowany przez Gildię od trzech miesięcy

RP:
  - uderza młotem przed każdą odpowiedzią
  - <przy pytaniach o Gildię> zaczyna sprzątać warsztat

REL:
  - **Thordin**+ brat - jedyna osoba której ufa
  - 🏛️ **Gildia Cieni**- szantażysta

APP:
  - ogromne dłonie, blizna przez prawą brew
  - zawsze w fartuchu, nawet poza kuźnią
```

---

## Status i ukończenie

Domyślnie każda encja jest *aktywna* i ma znaczenie w grze. Dzięki temu nie musimy oznaczać niczego specjalnie podczas pisania notatek — dopiero gdy coś traci istotność.

### Przekreślenie

Przekreślenie `~~tekst~~` unieważnia istotność encji w sesji — wzrok automatycznie ją pomija, ale zawartość zostaje w notatkach jako kontekst. Może to być ukończenie, dezaktualizacja czy pominięcie. Przekreślenie dotyczy zarówno pojedynczych encji w trybie liniowym, jak i całych nagłówków sekcji.

```markdown
~~🔎 **Świeże ślady** wozu na drodze~~ — trop nieaktualny
```

```
### 📍 Karczma Pod Rakiem — aktywna lokacja

### ~~📍 Karczma Pod Rakiem~~ — scena minęła lub lokacja nie ma już znaczenia

### ~~📍 ❌ Karczma Pod Rakiem~~ — scena nie doczekała wykorzystania
```

### Zadania

Znaczniki `- [ ]` i `- [x]` oznaczają że encja jest **jawnym zadaniem** — czymś, co gracze wyraźnie chcą lub powinni zrobić. Te znaczniki nakładają charakter celu do osiągnięcia na encję.

`- [ ]` to cel wciąż otwarty. `- [x]` to cel ukończony — zostaje jako ślad, nie znika.

Różnica wobec przekreślenia jest intencyjna: przekreślenie unieważnia istotność i pozwala wzrokowi ominąć encję bez tracenia kontekstu. `- [x]` mówi *zakończone* — encja nadal ma wagę jako potwierdzenie ukończenia.

```markdown
- [ ] **Wyprowadzić jeńców** przed świtem <magazyn nr 7> wymaga klucza lub włamania
- [x] **Klucz do magazynu** zdobyć od Jimsa

👤 **Borgrim**+
kowal, wie o tunelu za karczmą
- // szantażowany przez Gildię
- [ ] przekonać go do zeznań {Persw DC12}
```

---

## Progresja

Progresja to sekwencja zdarzeń, która przebiega automatycznie tak długo, jak gracze jej nie przerwą. Każdy krok progresji jest numerowany, ponieważ ich kolejność ma znaczenie — drugi krok zakłada, że pierwszy już się wydarzył.

Każdy krok progresji jest **zdarzeniem** albo **skutkiem zdarzeń**. Kontekst `<>` może modyfikować interpretację kroku (np. uruchamiać skutek w określonym stanie sceny), ale sam w sobie nie jest krokiem progresji ani nie rozpoczyna zdarzenia.

```markdown
### ⚡ Progresja: Noc na molo

1. Wybija północ -> straż zmienia wartę -> chwilowe okno bez obserwacji
2. !! Kapitan przybywa [zna twarze BG z listy gończej]
3. <BG użyli ognia> -> pożar na magazynie nr 7 -> chaos, wszystkie warty na molo
4. O świcie karawana odpływa — wszystko stracone
```

Emoji `⚡` w nagłówku sygnalizuje, że scena jest pod presją czasu i każde zwlekanie graczy ma konsekwencje. Inne emoji, np. 🔎 mogą sygnalizować spokojniejszą progresję.

Nieużyte ostatecznie kroki progresji przekreślamy: `2. ~~!! Kapitan przybywa~~`. W ten sposób zaznaczamy, jaki był wynik sekwencji.

Kroki progresji zapisujemy zazwyczaj w formie liniowej. Pozwala to skanować całą progresję jednym spojrzeniem — wszystkie informacje o kroku są w jednym miejscu.

Jeśli gracze mogą zablokować lub zmienić bieg progresji, dodajemy osobny krok opisujący tę możliwość. Alternatywnie dodajemy `//` jako sekret MG z wyjaśnieniem, co się stanie przy interwencji graczy.

```markdown
### 🔎 Progresja: Dochodzenie o kradzieży serów

1. Kupiec skarży się głośno na rynku -> plotka się rozchodzi -> mieszkańcy zaczynają podejrzewać siebie nawzajem
2. <BG nie szukają sprawcy> sołtys ogłasza nagrodę -> do wioski przybywa łowca nagród
3. !! Prawdziwy sprawca zaczyna zacierać ślady [kowal ukrył sery w tunelu]
4. // <BG nie rozwiązują sprawy do zmroku> łowca nagród aresztuje pierwszą podejrzaną niewinną osobę
```

---

## Symbole encji w nagłówkach

Emoji w nagłówku sekcji jest opcjonalne. Większość nagłówków obchodzi się bez niego. To stan domyślny, ponieważ wpisanie emoji wymaga oderwania rąk od klawiatury. Dodajemy je tylko wtedy, gdy typ encji nie jest oczywisty z kontekstu albo gdy chcemy przyspieszyć skanowanie w długich notatkach.

Gdy emoji jest obecne, stoi przed nazwą i określa typ encji. Wzrok rozpoznaje typ zanim przeczyta nazwę, a tekst zaraz po emoji to nazwa encji w świecie gry.

Emoji typu używamy wyłącznie przy pierwszej deklaracji encji. W relacjach, odnośnikach i dalszych wzmiankach piszemy już tylko imię, ponieważ encja jest w tym momencie znana czytelnikowi.

Encja może być jednocześnie nagłówkiem markdownowym (`###`, `####`), jeśli jest dostatecznie złożona by mieć całą sekcję dokumentu. W takim wypadku nadrzędny nagłówek `##` pełni rolę kategorii — `## Miejsca`, `## Postacie`, `## Frakcje` — a encje pod nim siedzą jako `### 📍 Dry Gulch`. Unikamy w ten sposób duplikacji nazwy w nagłówku sekcji i pierwszej linii bloku.

```markdown
## Miejsca w kraju Bracham
Bracham to kraj w którym znajduje się kampania.

### 📍 Suchy Wąwóz
miasteczko górnicze, sześć budynków, jedno wyjście

#### 📍 Magazyn Cery
przy zachodniej ścianie, zamknięty od trzech dni

#### 👤 Borgrim
kowal, główny informator BG
```

| Emoji | Typ encji |
|---|---|
| `📍` | lokacja lub miejsce |
| `👤` | BN, postać niezależna |
| `⚔️` | starcie, walka |
| `🎭` | scena z priorytetem na odgrywanie ról i relacje |
| `🗺️` | region, obszar lub mapa |
| `⚡` | progresja, presja czasu |
| `🏛️` | frakcja, organizacja |

### Łączenie symboli

Domyślnie encja nosi jeden symbol. Dopuszczamy jednak wyjątek: modyfikator (np. `!!` lub `!?`) może stać przed symbolem typu encji. Kolejność jest zawsze stała — modyfikator pierwszy, typ drugi.

```markdown
!! 👤 **Kapitan Varn**- zna twarze BG    ← krytyczny BN
!? 👤 **Mira**+ handlarka map            ← rewelacja dotycząca postaci
```

`!! 👤` natychmiast sugeruje: "ta postać jest ważna". Wzrok napotyka alarm (`!!`) zanim zdąży przeczytać imię.

Więcej niż dwa symbole z rzędu — nawet jeśli każdy z nich jest sensowny osobno — spowalniają skanowanie zamiast je przyspieszać. `🔎 !! 👤` jest nieczytelne i staramy się tego unikać.

---

## Emoji jako kompresja treści

Te emoji nie identyfikują typu encji, tylko zastępują zdanie lub dwa opisujące rolę informacji w grze. Używamy ich oszczędnie — tylko wtedy, gdy zastępują na tyle dużo tekstu, żeby oszczędność była realna. Pojedyncze emoji bez wyraźnej kompresji jest stratą uwagi czytelnika.

| Emoji | Kompresja |
|---|---|
| `⚡` | scena eskaluje automatycznie, każde zwlekanie graczy ma konsekwencje |
| `🎭` | emocjonalne centrum sesji, priorytet na relacje a nie mechanikę |
| `🧩` | gracze mogą lub powinni połączyć tę informację z innym wątkiem |
| `⚠️` | pułapka lub niebezpieczeństwo niewidoczne dla graczy |
| `🌀` | zwrot akcji, gracze spodziewają się czegoś innego |
| `🔑` | informacja lub przedmiot odblokowujący kolejny wątek |
| `🔎` | informacja możliwa do odkrycia, dostępna dla graczy jeśli szukają |
| `🏆` | nagroda lub skarb, konkretny łup |

---

## Bloki specjalne

### Treści nienadające się do kompresji

Proza, dialog i opisy to materiał, którego nie da się skrócić bez utraty sensu. Zapisujemy je w cytacie blokowym (`>`) z emoji-prefiksem na początku. Pionowa kreska cytatu sprawia, że oko od razu rozpoznaje blok jako inną klasę treści — niedoreferalną, do odczytania w całości.

W markdownie cytat blokowy kaskaduje na kolejne linie automatycznie — wystarczy `>` na pierwszej linii, dalsze są kontynuacją tego samego bloku. Powtarzamy `>` tylko gdy chcemy rozpocząć nowy blok cytatu z nowym emoji-prefiksem.

```markdown
> 📢 "Myślałem że utonęła. Tyle miesięcy sam..."
Ręce mu się trzęsą. Patrzy w podłogę, nie w oczy.

> 🌐 Usta posągu ziają ciemnością. Żółtawa maź sączy się po zboczu,
zostawiając za sobą wypalone pasma ziemi i ciszę, której tu nie powinno być.

> 📜 Atrament brązowy, pismo staranne, pieczęć złamana.
*"Jeśli Vareth się dowie o tym spotkaniu — obaj zginiemy."*
```

W treściach mówionych krótkie wypowiedzi BN inline zapisujemy backtikami: `\`tak właśnie powiedział\``. Dłuższe wypowiedzi i pełne sceny dialogowe trafiają do bloku z prefiksem `📢`.

| Prefiks | Typ treści |
|---|---|
| `📢` | tekst wypowiadany przez MG na głos — narracja mówiona lub dialog BN, wypowiadany swobodnie |
| `🌐` | tekst dla MG, czytany dla siebie, nie w celu wypowiedzenia — opis sytuacji, klimat, informacje dla MG które nie mają znaczenia dla graczy |
| `📜` | tekst istniejący w świecie gry — listy, inskrypcje, dokumenty fikcyjne, do pokazania graczom |

### Mechanika zewnętrzna

GRIM jest agnostyczny systemowo — nie narzuca sposobu zapisu statystyk, zdolności ani efektów mechanicznych z konkretnych gier. Istnieją dwa podejścia w zależności od sytuacji.

Gdy mechanikę zapisujemy własnymi słowami, wstawiamy ją jako cytat blokowy z nagłówkiem `> {{ Tytuł`. Otwarte `{{` sygnalizuje że to warstwa mechaniczna, a nie proza. Cały blok czyta się jako mechaniczny opis encji.

```markdown
> {{ Bestow Corruption
> Gdy cel w krótkim zasięgu wykonuje rzut, możesz użyć triggered action i dać mu
> 1k3 bonusy. Jeśli cel korzysta z benefitu, zyskuje 1 punkt Zepsucia.
```

Pełne stat blocki z systemu lub dokładną mechanikę — z oryginalnymi polami, wartościami i formatem — najlepiej wklejać dosłownie jako code block lub jako zrzut ekranu. Przepisywanie ich na format GRIM nie daje zysku czytelności, a traci precyzję.

### Tabele

Do treści tabelarycznych — tabele losowe, zestawienia ekwipunku, tabele nawigacji, procedury z wieloma wynikami — używamy standardowych tabel markdown. Tabele nie są encjami GRIM i nie stosujemy do nich symboliki systemu, chyba że dane w komórce są encją (wtedy wewnątrz komórki możemy użyć normalnej notacji).

Gdy cała kolumna z definicji opisuje mechanikę, nie owijamy każdej komórki w `{}` — nagłówek kolumny pełni rolę warstwy. `{}` używamy tylko wtedy, gdy mechanika jest wstawiona w prozę albo wymieszana z innymi warstwami.

```markdown
| k6 | Wynik | Test | Efekt |
|---|---|---|---|
| 1-3 | Obornik | Spostrzeżenie CR | losowy zaczarowany przedmiot |
| 4-6 | Śmieci | Str CR | choroba lub mikstura przy sukcesie |
```

### Kontekst dla AI

Jeśli używasz modelu językowego do wsparcia przy prowadzeniu sesji, możesz dodać blok kontekstu w komentarzu HTML. Komentarz nie pojawia się w rendererze markdown, ale jest widoczny w surowym tekście — model odczyta go przy wklejeniu notatek do promptu.

Blok jest opcjonalny i może wystąpić w dokumencie wielokrotnie, w dowolnym miejscu. Piszemy w nim naturalnym językiem, bez użycia symboli systemu — to notatki dla modelu, nie dla MG.

```markdown
<!-- AI CONTEXT
tu wpisujesz co dusza zapragnie — klimat kampanii, powody decyzji fabularnych,
rzeczy dziejące się w tle, których nie chcesz mieć w głównych notatkach.
Model wchłonie to przy wklejeniu surowego tekstu do promptu.
-->
```

---

## Przykłady

Stopniowy przykład: jedna encja, każdy krok dokłada jedną warstwę — żeby było widać jak encja rośnie od skrótu do pełnego bloku.

------

**Krok 1.** Sam skrót myślowy. Wystarcza gdy MG dobrze zna postać i imię od razu przywołuje pełny obraz.

```markdown
**Borgrim**+
```

------

**Krok 2.** Skrót nie wystarcza — dopisujemy wyjaśnienie. Jedna fraza mówiąca kim postać jest i co MG musi o niej pamiętać.

```markdown
**Borgrim**+ kowal, wie o tunelu za karczmą
```

------

**Krok 3.** Dodajemy symbol typu encji i kontekst `<>` — Borgrim mówi o tunelu tylko w kuźni i tylko po zmroku, więc kontekst stoi przed wyjaśnieniem i zmienia jego interpretację.

```markdown
👤 **Borgrim**+ <w kuźni po zmroku> kowal, wie o tunelu za karczmą
```

------

**Krok 4.** Dodajemy mechanikę — jak MG sprawdzi czy gracze wyciągną z postaci informację.

```markdown
👤 **Borgrim**+ <w kuźni po zmroku> kowal, wie o tunelu za karczmą {Persw DC12}
```

------

**Krok 5.** Dodajemy sekret — informację której gracze nie znają, ale która wpływa na zachowanie postaci.

```markdown
👤 **Borgrim**+ <w kuźni po zmroku> kowal, wie o tunelu za karczmą {Persw DC12} // szantażowany przez Gildię
```

------

**Krok 6.** Dodajemy foreshadowing `<<<` — szantaż wyrasta z głębszego wątku który wybrzmi później.

```markdown
👤 **Borgrim**+ <w kuźni po zmroku> kowal, wie o tunelu za karczmą {Persw DC12} // szantażowany <<< Gildia pozbywa się członków
```

------

**Krok 7.** Encja jest zbyt złożona na jedną linię — pojawiają się relacje, subsekcje i wyzwalacz. Przechodzimy do trybu blokowego. Skrót myślowy staje się nagłówkiem, warstwy rozkładają się na osobne linie, subsekcje dostają skróty oznaczone `***kursywą i pogrubieniem***`.

```markdown
👤 **Borgrim**+
kowal, wie o tunelu za karczmą
- <w kuźni po zmroku> {Persw DC12 | DC18 -> opowiada o kontrakcie z Gildią}
- // szantażowany od trzech miesięcy

***Tunel za karczmą***
wejście zna tylko on i Thordin
- <po zmroku> -> da się zejść bez świadków

REL:
  - **Thordin**+ brat [Thordin odkrył tunel jako pierwszy]
  - **Anata** znajoma ze sklepu na rogu <na ulicy> sprzeda mu jabłka za 2 md

! pytają o kontrakt
- -> panikuje, zaprzecza, wychodzi
- // rozważał zerwanie <<< przy odpowiednim podejściu może być sojusznikiem
```

---

## Spis emoji

Tabela referencyjna wszystkich emoji używanych w systemie wraz ze sposobami ich wpisywania.

**Win+.** (lub `Win + ;`) otwiera wyszukiwarkę emoji Windows — wpisujemy frazę z kolumny poniżej i wybieramy emoji z listy.  
**:shortcode:** działa w Obsidian, Slack, GitHub i większości narzędzi z autouzupełnianiem emoji — zaczynamy pisać `:` i wybieramy z podpowiedzi.  
**Unicode** to kod punktu kodowego znaku. W Windows otwieramy Mapę Znaków (`charmap.exe`) i wklejamy kod w pole wyszukiwania. W niektórych edytorach (na przykład Word) wpisujemy kod i naciskamy `Alt+X`, żeby zamienić go na emoji.

| Emoji | Win+. wpisz | :shortcode: |
|---|---|---|
| 📍 | `okrągła pinezka` | `:round_pushpin:` |
| 👤 | `sylwetka popiersia` | `:bust_in_silhouette:` |
| ⚔️ | `skrzyżowane miecze` | `:crossed_swords:` |
| 🎭 | `maski teatralne` | `:performing_arts:` |
| 🗺️ | `mapa świata` | `:world_map:` |
| ⚡ | `wysokie napięcie` | `:zap:` |
| 🏛️ | `klasyczna budowla` | `:classical_building:` |
| 🧩 | `puzle` | `:jigsaw:` |
| ⚠️ | `ostrzeżenie` | `:warning:` |
| 🌀 | `cyklon` | `:cyclone:` |
| 🔑 | `klucz` | `:key:` |
| 🔎 | `prawa lupa` | `:mag_right:` |
| 🏆 | `trofeum` | `:trophy:` |
| 📢 | `głośnik` | `:loudspeaker:` |
| 🌐 | `kula ziemska z południkami` | `:globe_with_meridians:` |
| 📜 | `zwój` | `:scroll:` |
| ❌ | `znak krzyżyka` | `:x:` |
| ⏭️ | `następny utwór` | `:next_track_button:` |


---

*GRIM — Glance, Read If Missing autorstwa dudematthew [dudematthew](https://github.com/dudematthew) / [hipstersavage](https://discord.gg/users/hipstersavage)*