---
title: 'CManaging your files'
---

Overview of this page:<br/>
├── Managing your files<br/>
│    ├── Naming convention / File Structure<br/>
│    │   ├── Manga<br/>
│    │   ├── Comics<br/>
│    │   ├── eBooks<br/>
│    │   ├── PDF<br/>
│    │   └── Raw Images<br/>
│    │<br/>
│    └── Metadata<br/>
│        ├── ComicInfo.xml<br/>
│        │     + Count and number explained<br/>
│        │     + Different tools<br/>
│        │<br/>
│        └── Books metadata<br/>
│              + Different tools Used<br/>

===

<hr style="border:5px solid #4ac694"> </hr>
## File Structure
It's important to know how kavita parses the info from the files.

Kavita uses parsing (not folder structure) to determine what is a series and what belongs to each series. Due to this, you are not required to put all of one series in the same folder, however it is good practice.

Folder and File Structure TOC:
* [Comic File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/comics)
* [Manga File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/manga)
* [eBooks File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/ebooks)
* [PDF File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/managing-your-files/pdf)
* [Raw Images File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/managing-your-files/raw-images)

For all types of libraries, Kavita has an override for treating files as Specials. 

To force a Special status, the filename can use SP01, SP02 etc.

   /libraryroot/Series Name/Series Name SP01.cbz
    /libraryroot/Series Name/Specials/Series Name SP01 Special Name.cbz

This will take the file and force it to be a special. For it to identify as a special and not as the series from the filename, it will look up towards the library root and attempt to parse the series name from the folder names.<br/>
For example: `/libraryroot/Again!!/Specials/Again The After Story SP01.cbz`
will parse "`Again!!`" for the Series name and group the file as a special under Again!!

<hr style="border:5px solid #4ac694"> </hr>
## Metadata
Kavita uses metadata to parse Series Name, Volumes, Chapters...
<hr style="border:1px solid ##465176"> </hr>
### Comics and Manga
Comics and manga uses a ".xml" file at the root of the cbz,cbr,cb7... files

This file must be named ComicInfo.xml

The xml schema of this file can be found in the [Anansi Project webpage](https://anansi-project.github.io/docs/introduction)

You can find multiple tools to add metadata under [Misc section](https://wiki.kavitareader.com/en/admin/pages/guides-rework/misc)

#### Count
In order for a Series to give a publication status, if you have at least one "Count" defined within any ComicInfo from the series and it is not 0, then Kavita will assume the Series is Completed. Otherwise, it will be assumed Ongoing.
Ideally the value of this field should be the total number of volumes (manga) or issues (comics)

<hr style="border:2px solid grey"> </hr>
<hr style="border:2px solid #aac4ba"> </hr>
#### Release Year
Likewise with Age Rating, Release Year is a summation of the minimum year defined within a series that is at least 4 units long (> 1000).
### eBooks

