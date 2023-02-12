---
title: 'Managing your files'
taxonomy:
    category:
        - docs
    tag:
        - specials
        - metadata
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
 
<hr style="border:5px solid #4ac694">

# Naming convention / File Structure
It's important to know how Kavita parses the info from the files, so you can see what you want how you want.

Kavita uses parsing (not folder structure) to determine what is a series and what belongs to each series. Kavita requires that each series be in its folder and that no files are at root level of the library.

! Please Read [how the new scanner works](scanner/docs.en.md) prior to continuing with this article

!! **Important**: When parsing filenames, anything between parenthesis and parenthesis themselves will be removed from the series name. <br/>If you wish to separate series using `Series Name (2019)`, it's advised to change parenthesis to brackets `{` `}` and change series name in the UI

Folder and File Structure TOC:
* [Comic File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/comics)
* [Manga File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/manga)
* [eBooks File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/ebooks)
* [PDF File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/pdf)
* [Raw Images File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/raw-images)

For all types of libraries, Kavita has an override for treating files as Specials. 

[//]: # (TODO: Add more info related to specias)
## Specials

Kavita treats multiple types of files as "Specials" and will group them in a separate tab in series detail. Special marker (SP) will be removed from the UI title, however is used when ordering.

An entity is considered a special when a series can be parsed out of it, but no volume or chapter information is found:

```
Library Root
  ┖── Series Name
      ┖── Series Name.cbz
```
<hr style="border:1px solid #465176">
To force a Special status, the filename can include SP01, SP02, etc.
This will take the file and force it to be a special:

```
Library Root
  ┖── Series Name
      ┖── Series Name SP01 Special Name.cbz
```
<hr style="border:1px solid #465176">
Other keywords that are used to mark as special are `Specials`, `Omake`, `OneShot`, `Extra`, `Art Collection`, `Side Stories`:

```
Library Root
  ┖── Series Name
      ┖── Specials
          ┖── Series Name Omakes SP01.cbz
```
<hr style="border:1px solid #465176">
For it to identify as a special and not as the series from the filename, it will look up towards the library root and attempt to parse the series name from the folder names.<br/>
For example:

```
Library Root
  ┖── Again!!
      ┖── Specials
            ┖── Again The After Story SP01.cbz
```
Will parse `"Again!!"` for the Series name and group the file `"Again The After Story SP01.cbz"` as a special under the series `"Again!!"`
<hr style="border:1px solid #465176">

!!! Additionaly if the file is a `.cb*` file, you may set this value with the use of [ComicInfo metadata](#comicinfo) using the [format tag](#format)

! **Note**: Specials will fall back to the folder name for Series name. If you have a different name than the series files, then your special may not properly group.

<hr style="border:5px solid #4ac694">

## Volumes
In order for something to be parsed as having a volume, a volume must be on the filename.

Volume means:
* v1
* vol 1
* vol. 1
* volume 01
* Vol 7.5
* Volume.2000
* 卷2
* 册2
* 2巻
* t. 2
* tome 2
* 
!!! Additionaly if the file is a `.cb*` file, you may set this value with the use of [ComicInfo metadata](#comicinfo) using the `volume tag`

# Metadata
Kavita uses metadata to parse Series Name, Volumes, Chapters, Special Status, etc... 

Kavita reads metadata from within your archives (cbz, cbr, c7, cbt) and epub files. If your archives contain metadata, it will override any parsed information from the file**name**

You can find multiple tools to add metadata under [Misc section](https://wiki.kavitareader.com/en/guides/misc#external-tools)

<hr style="border:2px solid #4ac694">


### General Overview on how Kavita reads certain metadata tags


| EPUB Tag           | Is  | In ComicInfo           | Is  |            Equivalent In Kavita            |
|:-------------------|:---:|:-----------------------|:---:|:------------------------------------------:|
| `Description`      |  →  | `Summary`              |  →  |                  Summary                   |
| `Creators`         |  →  | `Writer`               |  →  |                  Writers                   |
| `Pubishers`        |  →  | `Publisher`            |  →  |                 Publisher                  |
| `Publication Date` |  →  | `Month`, `Day`, `Year` |  →  | Release Date<br/>(Release Year for series) |
| `Title`            |  →  | `Title`                |  →  |               Chapter Title                |
| `Subjects`         |  →  | `Genre`                |  →  |                   Genres                   |
|                    |     | `Tags`                 |  →  |                    Tags                    |
|                    |     | `AgeRating`            |  →  |                 Age Rating                 |

### Comics and Manga
Comics and manga use a ".xml" file at the root of the cbz, cbr, cbt, cb7 files

This file must be named ComicInfo.xml and be at the root of the archive.

The XML schema of this file can be found in the [Anansi Project webpage](https://anansi-project.github.io/docs/comicinfo/schemas/v2.1). We support v2.1 (draft).

! **Note**: Kavita currently supports the following custom tags: 
- `<LocalizedTitle>` : Contains optional localized series name. 

<hr style="border:2px solid #4ac694">

### eBooks
EPUB files do not have a ComicInfo.xml, but they do have some limited metadata in the OPF file.
See the table above to know what tags do kavita read from the OPF file

!**Note:** OPF metadata files must be **inside** the `.epub` file, or it won't be read.  

 

<hr style="border:5px solid #4ac694">

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

<hr style="border:1px solid #465176">

#### Count
Kavita will set the Publication Status on a series for you based on this tag

- If you have at least one "Count" defined within any ComicInfo from the series, and it is not 0, then Kavita will assume the Series is Ended. Otherwise, it will be assumed Ongoing.

- If the Count matches the Volume count or Chapter count, then Kavita will assume the Series is Completed (you own all items of the series)

- Ideally, the value of this field should be the total number of volumes (manga) or issues (comics)

<hr style="border:1px solid #465176">

#### Release Year

Likewise with Age Rating, Release Year is a summation of the minimum year defined within a series that is at least 4 units long (> 1000).

<hr style="border:1px solid #465176">

#### Publication Status
Kavita will set the Publication Status on a series for you based on the underlying ComicInfo. 

If you have at least one ComicInfo with the `Count` property, then Kavita will at least mark the series as Ended.

Kavita will also check if the number of Volumes or Chapters matches this exactly and if so, will mark the series as Completed.

[//]: # (TODO: Add locked section rel link)
This logic will only run if the field is not [locked](../04.get-started-using-your-library/02.adding-and-editing-metadata/default.en.md#locking-fields). At any time you can hover over the tag badge in Series Detail to view how many issues or volumes you are missing. 

<hr style="border:1px solid #465176">

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
