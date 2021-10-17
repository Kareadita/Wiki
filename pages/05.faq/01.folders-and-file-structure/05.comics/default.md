---
title: Comics
---

### Comics Structure

Kavita parses Comics just like it does Manga but uses additional keyword identifiers. If you are having trouble, you might want to look at the different cases we have in [our code](https://github.com/Kareadita/Kavita/blob/develop/API.Tests/Parser/ComicParserTests.cs) and what is supported. The following will give you a glimpse.

The same naming conventions work with Comics.

* /libraryroot/Series Name/Series Name v01.cbz  
* /libraryroot/Series Name/Series Name v02.cbz  
* /libraryroot/Series Name/Series Name v03 c01.cbz  

In order for something to be parsed as having a volume, a volume must be on the filename. Volume means:
* v1
* vol 1
* vol. 1
* volume 01
* Vol 7.5
* Volume.2000

The following will be parsed as "Chapters", which may naturally group into a Volume entity if a volume is on the file iteslf.
* Invincible 070.5 - Invincible Returns 1 (2010) (digital) (Minutemen-InnerDemons).cbr -> Chapter 70.5
* Batman & Wildcat (1 of 3) -> Chapter 1
* Amazing Man Comics chapter 25 -> Chapter 25
* Superman v1 024 (09-10 1943) -> Volume 1 Chapter 24
* Y - The Last Man #001 -> Chapter 1
* Batgirl Vol.2000 #57 (December, 2004) -> Chapter 57
* Babe 01 -> Chapter 1


! If you have multiple comics from different years, you can name them as "Fables 2004" and "Fables 1989". Then in Kavita's UI, you can rename the "Name" field to be "Fables (2004)" and "Fables (1989)" so they are separate series. This workaround is the only way for different releases of the same series to be supported in Kavita.

Comics also have a list of special keywords that will mark it as a special. Some of these are:
* Book
* Conpendium
* OneShot
* Extra
* FCBD
* TPB
* Absolute 
* Preview
* Omnibus

 