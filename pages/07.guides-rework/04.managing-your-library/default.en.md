---
title: 'Managing your library'
media_order: LibraryActions.webp
---

Page overview
├── Managing your library<br/>
│    · Scanning<br/>
│        + What happens during scan<br/>
│    · Analylist<br/>
│        + What happens during Analysis<br/>
│    · Refresh covers<br/>

<hr style="border:5px solid #4ac694"> </hr>
## Scanning
Scanning a library makes Kavita check its folders and sub-folders for new or removed items (books, archive files, etc). If new media is found, it then pulls it into the library. You can think of scanning as “check for new or changed content”. 
! **Important**:<br/>- First scans are often slow, especially on networked storage. Be patient<br/>- The Kavita Homepage and Library info, will not be updated throughout the scan. They will be updated in chunks of 50 series at a time. 

<hr style="border:2px solid #4ac694"> </hr>
### What happens during a Scan?
Kavita will generate a library representation of your files on disk. A Kavita library does _not_ represent exactly your folder structure. Kavita uses filenames and some limited folder names to parse out the series, volume, chapter, etc from the file and group them. Books like epub, will use the metadata within the epub to perform grouping. 

Kavita also reads metadata from within your archives (cbz, cbr, c7, cbt) and epub files, using the ComicInfo.xml format. If your archives contain metadata, it will override any parsed information from the file. You can read up more about metadata [here](https://wiki.kavitareader.com/en/guides-rework/managing-your-files#metadata).

If the underlying file has not been modified between scans, Kavita will not do extra processing on the file. 

<hr style="border:5px solid #4ac694"> </hr>
## Analyze books
Analysis is automatically performed when content is added to your Library. In rare cases, new versions of Kavita may update the media analysis capabilities to correct something or add the ability to detect new things. In those cases, content may be re-analyzed when you access it after the new server version is installed.

<hr style="border:2px solid #4ac694"> </hr>
### What happens during Analysis?
Whenever an item is added to one of your Libraries, Kavita performs some analysis on it to gather information. In addition, files analyzed will also be refreshed for covers in the following conditions:
- A cover image is not present on the item
- The user requested a refresh of covers manually from series/library context menu
- The file has been modified since last scan

<hr style="border:1px ##4ac694 solid "> </hr>
#### Generate default artwork
During analysis, artwork will automatically be grabbed from the media file. The first page will be used for poster/thumbnail type purposes unless a file named cover is within the archive. Epubs have cover images specified within the metadata (opf).
<hr style="border:2px solid #4ac694"> </hr>
### How to analyze?

You can analyze content in multiple ways: for a book, for a series, or even for an entire Library.

Look for the **Action Menu** icon of three vertical dots.

![LibraryActions](LibraryActions.webp?cropResize=300,300 "LibraryActions") ![MangaActions](MangaActions.webp?cropResize=300,300 "MangaActions")![BooksActions](BooksActions.webp?cropResize=300,300 "BooksActions")

! **Note**: Depending on the size of your Library, analysis may take a while.

[//]: # (Comment: Add this if more "###" are added      <hr style="border:2px solid #4ac694"> </hr>   )