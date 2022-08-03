---
title: 'Scanning and Refreshing Metadata'
media_order: 'LibraryActions.jpg,MangaActions.jpg,BooksActions.jpg'
---

Once a library has been created, it is processed by Kavita so that all the files are matched to series and metadata is gathered. As time goes on, you’ll add and remove files to the libraries or make other changes that mean the library is no longer up-to-date. You can invoke the Scan libraries task from the actions menu to bring them up-to-date. Scan Library and Refresh Covers for a library do different things.

## Scan Library Files

Scanning a library makes Kavita check its folders and sub-folders for new or removed items (books, archive files, etc). If new media is found, it then pulls it into the library. You can think of scanning as “check for new or changed content”. The Kavita Homepage and Library info, will not be updated throughout the scan, in chunks of 50 series at a time. First scans are often slow, especially on networked storage. Be patient.

All files that have changed after a scan will have their covers refreshed if applicable.

You should Scan Library Files if you have:
- Added or deleted files or folders
- Renamed a file or folder
- Moved files or folders from one location to another

Scanning a Library is an automated task that by default runs once a day at midnight. You can invoke it at any given time from the Library actions menu from the UI.

## Scanning Just a Series
If you only need to refresh data for a given series, you can do that by invoking the Scan Series from the Series context menu. This logic is the same as a Scan library, but only on the scale of the series and as such, is much faster. Like for a Scan Library, covers will be checked after the fact on the scan. 


## What happens during a Scan?

Kavita will generate a library representation of your files on disk. A Kavita library does _not_ represent exactly your folder structure. Kavita uses filenames and some limited folder names to parse out the series, volume, chapter, etc from the file and group them. Books like epub will use the metadata within the epub to perform grouping. 

Kavita also reads metadata from within your archives (cbz, cbr, c7, cbt) and epub files, using the ComicInfo.xml format. If your archives contain metadata, it will override any parsed information from the file. You can read more about metadata [here](https://wiki.kavitareader.com/en/guides/metadata).

If the underlying file has not been modified between scans, Kavita will not do extra processing on the file. 


## Analyze books

Analysis is automatically performed when content is added to your Library. In rare cases, new versions of Kavita may update the media analysis capabilities to correct something or add the ability to detect new things. In those cases, content may be re-analyzed when you access it after the new server version is installed.

### What happens during Analysis?

Whenever an item is added to one of your Libraries, Kavita performs some analysis on it to gather information. In addition, files analyzed will also have their covers refreshed in the following conditions:
- A cover image is not present on the item
- The user requested a refresh of covers manually from the series/library context menu
- The file has been modified since the last scan


#### Generate default artwork

During analysis, artwork will automatically be grabbed from the media file. The first page will be used for poster/thumbnail type purposes unless a file named cover is within the archive. Epubs have cover images specified within the metadata (opf).

### Analyze your content

You can analyze content in multiple ways: for a book, for a series, or even for an entire Library.

Look for the **Action Menu** icon of three vertical dots.

![LibraryActions](LibraryActions.jpg?resize=300,300 "LibraryActions") ![MangaActions](MangaActions.jpg?resize=300,300 "MangaActions")![BooksActions](BooksActions.jpg?resize=300,300 "BooksActions")


! **Note**: Depending on the size of your Library, analysis may take a while.

## Automatic Library Refresh

Kavita is set by default to Scan all Libraries Daily (this can be changed under the General Tab in Admin Settings), and to perform a Database Backup Weekly.

## Refresh Covers

Refreshing Covers for a library, series, or individual book cause the covers for the item to be regenerated, even if it already has a cover set. You can think of refreshing as “update covers for the requested item even if it already has one”.

You should refresh covers on a library or individual item if:
- You’ve edited a file to change the first picture or added a cover.jpg file


### For information regarding best file Naming practices see our FAQ Section

Folders and File Structures FAQ starts [here](https://wiki.kavitareader.com/faq/folders-and-file-structure).
