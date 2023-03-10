---
title: Metadata
---

Kavita uses metadata to parse Series Name, Volumes, Chapters, Special Status, etc... 

Kavita reads metadata from within your .c* archives (cbz, cbr, c7, cbt) and epub files. If your archives contain metadata, it will override any parsed information from the file**name**

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
- `<LocalizedSeries>` : Contains optional localized series name which will display in Kavita. Will allow searching for either series name. Will group files that have the localized name and the series name together as one series.

<hr style="border:2px solid #4ac694">

### eBooks
EPUB files do not have a ComicInfo.xml, but they do have some limited metadata in the OPF file.
See the table above to know what tags do kavita read from the OPF file

! **Note:** OPF metadata files must be **inside** the `.epub` file, or it won't be read.  

 

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

#### SeriesGroup

The SeriesGroup tag can contain comma delimited strings that will either create or update existing collections in Kavita if the Library has `Manage Collections` turned on (default is off). 

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
