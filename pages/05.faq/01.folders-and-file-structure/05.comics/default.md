---
title: Comics
---

### Comics Structure

Kavita parses Comics just like it does Manga but uses additional keyword identifiers. 

The same naming conventions work with Comics.

* /libraryroot/Series Name/Series Name v01.cbz  
* /libraryroot/Series Name/Series Name v02.cbz  
* /libraryroot/Series Name/Series Name v03 c01.cbz  

In addition, these cases will be parsed as a "Volume"
* Scott Pilgrim 02 - Scott Pilgrim vs. The World (2005) -> Volume 2
* Batman & Catwoman - Trail of the Gun 01 -> Volume 1
* Batman & Robin the Teen Wonder \#0 -> Volume 0

The following will be parsed as "Chapters", which may naturally group into a Volume entity.
* Invincible 070.5 - Invincible Returns 1 (2010) (digital) (Minutemen-InnerDemons).cbr -> Chapter 70.5
* Batman & Wildcat (1 of 3) -> Chapter 1
* Amazing Man Comics chapter 25 -> Chapter 25

! Comic Parsing is currently under review for a major enhancement and solidification on naming conventions. You can find the discussion [here](https://github.com/Kareadita/Kavita/issues/345).
 