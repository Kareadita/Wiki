---
title: 'Scanning, Analyzing, and Refreshing Metadata'
media_order: 'LibraryActions.jpg,MangaActions.jpg,BooksActions.jpg'
---

Once a library has been created, it is processed by Kavita so that all the files are matched to series and books, and metadata is gathered. As time goes on, you’ll add and remove books to the libraries or make other changes that mean the library is no longer up-to-date. You can Scan libraries to bring them up-to-date. Scan Library, and Refresh Metadata for a library do different things.

## Scan Library Files

Scanning a library makes Kavita check its folders and sub-folders for new or removed books. If it finds new media, it then pulls it into the library. You can think of scanning as “check for new or changed content”. The Kavita Homepage and Library info, will not be updated until the scan is complete.

All files that have changed after a scan will be Analyzed.

You should Scan Library Files if you have:
*Added or deleted files or folders
*Renamed a file or folder
*Moved files or folders from one location to another


## What happens during a Scan?

Kavita will generate a library representation of your files on disk. A Kavita library does _not_ represent exactly your folder structure.


## Analyze books

Analysis is automatically performed when content is added to your Library. In rare cases, new versions of Kavita may update the media analysis capabilities to correct something or add the ability to detect new things. In those cases, content may be re-analyzed when you access it after the new server version is installed.

### What happens during Analysis?

Whenever an item is added to one of your Libraries, Kavita performs some analysis on it to gather information. In addition, all files analyzed will also be refreshed for metadata.

#### Gather media properties

The primary purpose of media analysis is to gather information about that media item. All of the media you add to a Library has properties that are useful to know, such as:
*Container: ZIP, RAR, EPUB, etc.
*Images Format: JPEG, PNG, WEBP, etc.

Why, though? What use are these media properties? Your Server, together with your apps, can use this information to help determine whether (and how) content can be played.

For example: Imagine you have a CBR file with WEBP images, but you’re using Internet Explorer (which can’t read WEBP). Since the webreader knows what kind of content your browser can display and since your media analysis detected that the book has WEBP images, Kavita can convert those images to a compatible format (like JPEG) for you in order to let you read your book successfully.

#### Generate default artwork

During analysis, artwork will automatically be grabbed from a book file. The first page will be used for poster/thumbnail type purposes.

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
- A local file located inside a CBZ or CBR
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
