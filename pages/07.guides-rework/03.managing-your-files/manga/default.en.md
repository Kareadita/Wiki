---
title: Manga
---

### Manga Structure
A good structure would be:
`
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
`
 

### Manga Specials

Kavita treats multiple types of files as "Specials" and will group them in a separate tab in series detail. Special marker (SP) will be removed from the UI title, however is used when ordering. 

An entity is considered a special when:

1. A series can be parsed out of it, but no volume or chapter information is found.
```
Library Root
     ┖── Series Name
         ┖── Series Name.cbz```

2. There are keywords in the filename like "Specials", "Omake" "OneShot", "Extra", "Art Collection", "Side Stories"```
Library Root
    ┖── Series Name
         ┖── Specials
             ┖── Series Name Omakes SP01.cbz```

3. To force a Special status, the filename can use SP01, SP02 etc.
```
Library Root
    ┖── Series Name
         ┠── Series Name v01.cbz
         ┠── Series Name v02.cbz
         ┠── Series Name SP01.cbz
         ┖── Specials
             ┖── Series Name SP01 Special Name.cbz```

### Examples of Naming conventions supported out of the box
* Noblesse - Episode 406 (52 Pages).7z -> Noblesse Chapter 406
* \[Hidoi]\_Amaenaideyo\_MS_vol01_chp02.rar -> Amaenaideyo MS Vol 1 Chapter 2
* Transferred to another world magical swordsman v1.2 -> Transferred to another world magical swordsman Vol 1 Chapter 2
* Okusama wa Shougakusei c003 (v01) [bokuwaNEET] -> Okusama wa Shougakusei Vol 1 Chapter 3
* Goblin Slayer Side Story - Year One 025.5 -> Goblin Slayer Side Story - Year One Chapter 25.5
* Itoshi no Karin - c001-006x1 (v01) [Renzokusei Scans] -> Itoshi no Karin Chapters 1-6
* Beelzebub_53\[KSH].zip -> Beelzebub Chapter 53
* Killing Bites Vol. 0001 Ch. 0001 - Galactica Scanlations (gb) -> Killing Bites Vol 1 Chapter 1
* And [many more](https://github.com/Kareadita/Kavita/blob/develop/API.Tests/Parser/MangaParserTests.cs)...

### Supported but not preferred (v0.4.3 or higher)
```
└── Manga 2
    └── Vol. 1
        └── Ch.1 - Ch.3
            ├── 1.zip
            ├── 2.zip
            └── 3.zip
```            