---
title: 'Folders and File Structure'
visible: true
---

Kavita uses parsing (not folder structure) to determine what is a series and what belongs to each series. Due to this, you are not required to put all of one series in the same folder, however it is good practice.

Folder and File Structure TOC:

* [Manga](https://wiki.kavitareader.com/faq/folders-and-file-structure/manga)
* [eBooks](https://wiki.kavitareader.com/faq/folders-and-file-structure/ebooks)
* [PDF](https://wiki.kavitareader.com/faq/folders-and-file-structure/pdf)
* [Comics](https://wiki.kavitareader.com/faq/folders-and-file-structure/comics)
* [Raw Images](https://wiki.kavitareader.com/faq/folders-and-file-structure/raw-images)

For all types of libraries, Kavita has an override for treating files as Specials. 

To force a Special status, the filename can use SP01, SP02 etc.

    /libraryroot/Series Name/Series Name SP01.cbz
    /libraryroot/Series Name/Specials/Series Name SP01 Special Name.cbz

This will take the file and force it to be a special. For it to identify as a special and not as the series from the filename, it will look up towards the library root and attempt to parse the series name from the folder names. 
For example:
    /libraryroot/Again!!/Specials/Again The After Story SP01.cbz 
will parse "Again!!" for the Series name and group the file as a special under Again!!