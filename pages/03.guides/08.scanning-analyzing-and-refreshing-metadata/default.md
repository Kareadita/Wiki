---
title: 'Scanning and Refreshing Metadata'
media_order: 'LibraryActions.jpg,MangaActions.jpg,BooksActions.jpg'
---

Once a library has been created, it is processed by Kavita so that all the files are matched to series and metadata is gathered. As time goes on, you’ll add and remove files to the libraries or make other changes that mean the library is no longer up-to-date. You can invoke the Scan libraries task from the actions menu to bring them up-to-date. Scan Library, and Refresh Metadata for a library do different things.

## Scan Library Files

Scanning a library makes Kavita check its folders and sub-folders for new or removed items (books, archive files, etc). If new media is found, it then pulls it into the library. You can think of scanning as “check for new or changed content”. The Kavita Homepage and Library info, will not be updated until the scan is complete.

All files that have changed after a scan will have their metadata refreshed if applicable.

You should Scan Library Files if you have:
- Added or deleted files or folders
- Renamed a file or folder
- Moved files or folders from one location to another

Scanning a Library is an automated task that by default runs once a day at midnight. You can invoke it at any given time from the Library actions menu from the UI.


## What happens during a Scan?

Kavita will generate a library representation of your files on disk. A Kavita library does _not_ represent exactly your folder structure. Kavita uses filenames and some limited folder names to parse out the series, volume, chapter, etc from the file and group them. Books like epub, will use the metadata within the epub to perform grouping. 


## Analyze books

Analysis is automatically performed when content is added to your Library. In rare cases, new versions of Kavita may update the media analysis capabilities to correct something or add the ability to detect new things. In those cases, content may be re-analyzed when you access it after the new server version is installed.

### What happens during Analysis?

Whenever an item is added to one of your Libraries, Kavita performs some analysis on it to gather information. In addition, all files analyzed will also be refreshed for metadata. ** This is not always true. We only recalculate metadata if it isn't set, the user requests refresh metadata manually, or the file has been modified since last scan **

#### Generate default artwork

During analysis, artwork will automatically be grabbed from the media file. The first page will be used for poster/thumbnail type purposes unless a file named cover is within the archive. Epubs have cover images specified within the metadata.

### Analyze your content

You can analyze content in multiple ways: for a book, for a series, or even for an entire Library.

Look for the **Action Menu** icon of three vertical dots.

![LibraryActions](LibraryActions.jpg?resize=300,300 "LibraryActions") ![MangaActions](MangaActions.jpg?resize=300,300 "MangaActions")![BooksActions](BooksActions.jpg?resize=300,300 "BooksActions")


! **Note**: Depending on the size of your Library, analysis may take a while.

## Automatic Library Refresh

Kavita is set by default to Scan all Libraries Daily (this can be changed under the General Tab in Admin Settings), and to perform a Database Backup Weekly.

## Refresh Metadata

Refreshing Metadata for a library, series, or individual book causes the metadata for the item to be refreshed, even if it already has metadata. You can think of refreshing as “update metadata for the requested item even if it already has some”.

You should refresh a library or individual item if:
- You’ve changed options for the library
- You’ve edited a file to change the first picture or added a cover.jpg file

Metadata is gathered from the following sources:
- A local file located inside an archive file (CBZ, CBR, CB7, ZIP, RAR (RAR5 not supported), 7ZIP)
- The metadata of an EPUB file

The metadata refresh is dependent of the type of Library created.

#### Book Metadata

This will import the following fields from the filename into Kavita:

- `Title`, `Summary`, `Number` as their Kavita equivalent

#### Series Metadata

This will import the following fields from the .opf file for the Series info into Kavita.

- The `Series` and `Volume` tags will be used to overwrite the title of the Series, in the form `<Series> (<Volume>)`, or just `<Series>` if the `Volume` tag is not present or if the `Volume` is `1`. If multiple values are present, the most frequent value from all books will be used.

### For information regarding best file Naming practices see our FAQ Section

Folders and File Structures FAQ starts [here](https://wiki.kavitareader.com/faq/folders-and-file-structure).
