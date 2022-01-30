---
title: 'Managing your files'
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
* [eBooks File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/managing-your-files/ebooks)
* [PDF File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/managing-your-files/pdf)
* [Raw Images File Structure](https://wiki.kavitareader.com/en/guides-rework/managing-your-files/managing-your-files/raw-images)

The parsing order is the following
1. Metadata file
2. File name
3. Folder name

For all types of libraries, Kavita has an override for treating files as Specials. 

To force a Special status, the filename can use SP01, SP02 etc.

   /libraryroot/Series Name/Series Name SP01.cbz
    /libraryroot/Series Name/Specials/Series Name SP01 Special Name.cbz

This will take the file and force it to be a special. For it to identify as a special and not as the series from the filename, it will look up towards the library root and attempt to parse the series name from the folder names.<br/>
For example:
    /libraryroot/Again!!/Specials/Again The After Story SP01.cbz 
will parse "Again!!" for the Series name and group the file as a special under Again!!

<hr style="border:5px solid #4ac694"> </hr>
## Metadata
Kavita uses metadata to parse Series Name, Volumes, Chapters...
<hr style="border:1px solid ##465176"> </hr>
### Comics and Manga
<hr style="border:1px solid ##465176"> </hr>
### eBooks

