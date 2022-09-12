---
title: 'Managing your files'
taxonomy:
    tag:
        - Metadata
        - ComicInfo
        - Naming
        - Scan
        - 'Refresh Covers'
metadata:
    'og:description': 'This page covers everything related to file management. This includes proper naming, local metadata, and how to update files in Kavita.'
    'og:title': 'Managing your files | Kavita Wiki'
    'og:url': 'https://wiki.kavitareader.com/en/guides-rework/managing-your-library'
admin: {  }
---

#### Page overview
- [Naming convention / File Structure](#naming-convention--file-structure)<br/>
  - [Specials](#specials)
- [Metadata](#metadata)
  - [Metadata Tags Mapping](#general-overview-on-how-kavita-reads-certain-metadata-tags) (How kavita uses certain metadata tags)
  - [Comics And Manga](#comics-and-manga)
  - [eBooks](#ebooks)
  - [ComicInfo](#comicinfo)
<hr style="border:5px solid #4ac694"> </hr>

# Naming convention / File Structure
It's important to know how Kavita parses the info from the files, so you can see what you want how you want.

[//]: # (TODO: Add link)
Kavita uses parsing (not folder structure) to determine what is a series and what belongs to each series. Kavita requires that each series be in it's folder and that no files are at root level of the library.

! Please Read [how the new scanner works]() prior to continue with this read

Folder and File Structure TOC:
* [Comic File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/comics)
* [Manga File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/manga)
* [eBooks File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/ebooks)
* [PDF File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/pdf)
* [Raw Images File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/raw-images)

For all types of libraries, Kavita has an override for treating files as Specials. 

[//]: # (TODO: Add more info related to specias)
## Specials

To force a Special status, the filename can use SP01, SP02, etc.
```
Library Root
  ┖── Series Name
      ┖── Series Name SP01.cbz
```
```
Library Root
  ┖── Series Name
      ┖── Specials
            ┖── Series Name SP01 Special Name.cbz
```

This will take the file and force it to be a special.

For it to identify as a special and not as the series from the filename, it will look up towards the library root and attempt to parse the series name from the folder names.<br/>
For example:
```
Library Root
  ┖── Again!!
      ┖── Specials
            ┖── Again The After Story SP01.cbz
```
Will parse `"Again!!"` for the Series name and group the file `"Again The After Story SP01.cbz"` as a special under the serie `"Again!!"`

Additionaly if the file is a `.cb*`, you may set this value with the use of [ComicInfo metadata](#comicinfo) using the [format tag](#format)

<hr style="border:5px solid #4ac694"> </hr>

# Metadata
Kavita uses metadata to parse Series Name, Volumes, Chapters...
Kavita reads metadata from within your archives (cbz, cbr, c7, cbt) and epub files. If your archives contain metadata, it will override any parsed information from the file. 

<hr style="border:2px solid #4ac694"> </hr>


### General Overview on how kavita reads certain metadata tags

[//]: # (TODO: Add a column that express what tags would be mapped to kavita
            This means X tag in epub is X in comicinfo. Both are shown as X in kavita )

| EPUB Tag          | Is  | In ComicInfo           | Is  | Equivalent In Kavita |
|:------------------|:---:|:-----------------------|:---:|:--------------------:|
| `Description`     |  →  | `Summary`              |  →  |                      |
| `Cretors`         |  →  | `Writer`               |  →  |                      |
| `Pubishers`       |  →  | `Publisher`            |  →  |                      |
| `Pubication Date` |  →  | `Month`, `Day`, `Year` |  →  |                      |
| `Title`           |  →  | `Title`                |  →  |                      |
| `Subects`         |  →  | `Genre`                |  →  |                      |
`
### Comics and Manga
Comics and manga use a ".xml" file at the root of the cbz, cbr, cbt, cb7 files

This file must be named ComicInfo.xml and be at the root of the archive.

The XML schema of this file can be found in the [Anansi Project webpage](https://anansi-project.github.io/docs/comicinfo/schemas/v2.1). We support v2.1 (draft).

You can find multiple tools to add metadata under [Misc section](https://wiki.kavitareader.com/en/guides/misc#external-tools)

<hr style="border:2px solid #4ac694"> </hr>

### eBooks
EPUB files do not have a ComicInfo.xml, but they do have some limited metadata in the OPF file.
See the table above to know what tags do kavita read from the OPF file

 

<hr style="border:5px solid #4ac694"> </hr>

## ComicInfo
### Tags that will cause specific behaviour in your kavita:
#### Age Rating

Age rating may vary between different files within a series. The Series will take the highest Age Rating (aka most mature) and use it from the files contained within. So for example, say you have:

Current tags from less restrictive to most restrictive: 

[//]: # (TODO: Add list from least restrictive to most restrictive)

* Issue 1 - PG
* Issue 2 - PG
* Issue 3 - M

The series will be M as that is the most mature rating in all Issues.

<hr style="border:1px solid #465176"> </hr>

#### Count

In order for a Series to give a publication status, if you have at least one "Count" defined within any ComicInfo from the series and it is not 0, then Kavita will assume the Series is Completed. Otherwise, it will be assumed Ongoing.
Ideally, the value of this field should be the total number of volumes (manga) or issues (comics)

<hr style="border:1px solid #465176"> </hr>

#### Release Year

Likewise with Age Rating, Release Year is a summation of the minimum year defined within a series that is at least 4 units long (> 1000).

<hr style="border:1px solid #465176"> </hr>

#### Publication Status
Kavita will set the Publication Status on a series for you based on the underlying ComicInfo. 

If you have at least one ComicInfo with the `Count` property, then Kavita will at least mark the series as Ended.

Kavita will also check if the number of Volumes or Chapters matches this exactly and if so, will mark the series as Completed.

[//]: # (TODO: Add locked section rel link)
This logic will only run if the field is not [locked](). At any time you can hover over the tag badge in Series Detail to view how many issues or volumes you are missing. 

<hr style="border:1px solid #465176"> </hr>

#### Format
If a Format is specified, that issue or volume may be forced into being treated as a Special (v0.5.4+). 

The following entries will cause this:
* Special
* Reference
* Director's Cut
* Box Set
* Box-Set
* Annual
* Anthology
* Epilogue
* One Shot
* One-Shot
* Prologue
* TPB
* Trade Paper Back
* Omnibus
* Compendium
* Absolute
* Graphic Novel
* GN
* FCBD 
