---
title: Metadata
published: true
date: '20-01-2022 10:56'
taxonomy:
    category:
        - docs
---

# Local Metadata (v0.5+)
Kavita is proud to be a member of the [Anasai Project](https://anansi-project.github.io/docs/introduction) and supports the latest draft of ComicInfo.xml (v2.1) along with EPUB metadata parsing. Local metadata can come from two sources: EPUB or ComicInfo.xml. 

## ComicInfo.xml
If a comicinfo.xml file is found within an archive, Kavita will read it and use that as the source of truth for the file. Most of the fields are straightfoward, but a few of them affect the Series. 

### Age Rating
Age rating may vary between different files within a series. The Series will take the highest Age Rating (aka most mature) and use it from the files contained within. So for example, say you have:
* Issue 1 - PG
* Issue 2 - PG
* Issue 3 - M
The series will be M as that is the most mature rating in all Issues.

### Count
In order for a Series to give a publication status, if you have at least one Count defined within the ComicInfo and it is not 0, then Kavita will assume the Series is Completed. Otherwise, it will be assumed Ongoing. 

### Release Year
Likewise with Age Rating, Release Year is a summation of the minimum year defined within a series that is at least 4 units long (> 1000). 


## EPUB
Some metadata is parsed from EPUBs to emulate a ComicInfo and provide some parity. The following fields can be pulled:
* Summary
* Writer
* Publisher
* Month
* Day
* Year
* Title
* Genre
