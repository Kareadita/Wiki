---
title: Manga
visible: true
---

### Manga Structure
A good structure would be:
```
Library Root
  ┖── Series Name
      ┠── Series Name v01.cbz
      ┠── Series Name v02.cbz
      ┠── Series Name v03.cbz
      ┖── Specials
        ┖── Series Name Omakes SP01.cbz
  ┖── Series Name 2
      ┠── Series Name 2 Vol.01 Ch.1.cbz
      ┠── Series Name 2 Vol.01 Ch.2.cbz
      ⋮
      ┖── Series Name 2 Vol.02 Ch.6.cbz
```

### Examples of Naming conventions supported out of the box

| Filename                                                        |               Parsed Series Name               | Volume | Chapter |
|:----------------------------------------------------------------|:----------------------------------------------:|:-------|:--------|
| `Noblesse - Episode 406 (52 Pages).7z`                          |                    Noblesse                    | 406    |         |
| `[Hidoi]_Amaenaideyo_MS_vol01_chp02.rar`                        |                 Amaenaideyo MS                 | 1      | 2       |
| `Transferred to another world magical swordsman v1.2`           | Transferred to another world magical swordsman | 1      | 2       |
| `Okusama wa Shougakusei c003 (v01) [bokuwaNEET]`                |             Okusama wa Shougakusei             | 1      | 3       |
| `Goblin Slayer Side Story - Year One 025.5`                     |      Goblin Slayer Side Story - Year One       |        | 25.5    |
| `Itoshi no Karin - c001-006x1 (v01) [Renzokusei Scans]`         |                Itoshi no Karin                 |        | 1-6     |
| `Beelzebub_53[KSH].zip`                                         |                   Beelzebub                    |        | 53      |
| `Killing Bites Vol. 0001 Ch. 0001 - Galactica Scanlations (gb)` |                 Killing Bites                  | 1      | 1       |
|                                                                 |                                                |        |         |
|                                                                 |                                                |        |         |
And [many more](https://github.com/Kareadita/Kavita/blob/develop/API.Tests/Parser/MangaParserTests.cs)...

### Supported but not preferred (v0.4.3 or higher)
```
└── Manga 2
    └── Vol. 1
        └── Ch.1 - Ch.3
            ├── 1.zip
            ├── 2.zip
            └── 3.zip
```            