---
title: EPUB
media_order: collectionmetadata.webp
visible: true
---

### EPUB Structure

EPUB are primarily parsed by metadata within the epub file (opf). Filenames are used only for Volume and Series, but metadata overrides everything. eBooks do not fall back to folders for parsing.

Kavita scans epubs in a 2 pass process. The first pass pulls from the internal metadata. If the Series is missing, the epub will use the title and if title missing, then will fallback to the filename parser. The second pass will use filename to fill in the missing information to be included in Kavita. If **volume** and **series** name can be parsed, then the book is treated like a manga or comic and will how Volume X in the Series detail for the individual books. Within the metadata, certain tags are used to group them into a series, like "Expanse".
[Calibre](https://wiki.kavitareader.com/en/guides/misc/calibre) eBook Management software can be used to edit epub metadata to include Series, Volume, and Title so that series with multiple books parse correctly into the same series. 
#### Epub Metadata
This will import the following fields from the Epub into Kavita:
* `dc:title` element as the _Title_ (this can be overridden by `calibre:series` or `belongs-to-collection` meta)
* `dc:description` element as the _Summary_
* `dc:subjects` elements as the _Genres_
* `dc:language` elements as the _Language_ (Kavita will only take the first)
* `dc:creator` elements as the _Writer_ (See Expanding People Metadata)
* `dc:identifier opf:scheme="isbn"` element as the _ISBN_
* `calibre:title_sort` element as _TitleSort_
* `calibre:series` element as _Name_ and _SortName_ (for the series)
* `calibre:series_index` element as _Volume_

The following meta properties will be imported into Kavita:
* `group-position` as _Volume_
* `belongs-to-collection` as _Name_ and _SortName_ (for the Series)
* `role` with `marc:relators`as _Person_ (See Expanding People Metadata)
* `title-type` with content of `collection` (See Collections/Reading List)
* `display-seq` as Reading List position (See Collections/Reading List)

##### Expanding People Metadata
In an epub (Kavita v0.7.3+), you can expand on people with not just author and publisher mappings, but can support the following:
* art/artist
* aut/author
* pbl/publisher
* trl/translator
* edt/editor
* ill/illustrator
* clr/colorist

In order to achieve this, you must refine the existing `dc:creator` tag with a `meta` tag. Both must exist otherwise the creator will be treated just as an author. See below, we are going to define that there is an editor:
```
<dc:creator id="id-1">Miya Kazuki</dc:creator>
<meta refines="#id-1" property="role" scheme="marc:relators">editor</meta>
```
##### Reading Lists and Collections
For libraries that are allowed to manage collections and reading lists (and Kavita v0.7.3+), Kavita can utilize epub metadata fields for this.

In the following example, we have just a single title here and the meta tag to refine this title and indicate that it is used for a collection. With just this, Kavita will generate a `Collection` tag.
```
<dc:title id="t1">A Dictionary of Modern English Usage</dc:title>
<meta refines="#t1" property="title-type">collection</meta>
```

If you add an additional tag of `display-seq` then Kavita will treat the collection as a reading list and generate the reading list with the following order. Note that if you have conflicts, Kavita will automatically reorder, so order may be skewed. 
```
<meta refined="#t1" property="display-seq">1</meta>
```

##### Grouping Series
Some books belong together, like in the example, Harry Potter. Sure, we can have each book as it's own series, but sometimes it's better to group them under one series. The ideal way to perform this grouping is by using `calibre:series` and `calibre:series_index` or `belongs-to-collection` and `group-position` for Epub 3.2 files. In the following, we can have our 2 harry potter books grouped together as one single Harry Potter Series (I am using Epub 2 for the first and Epub 3+ for the second):

```
<dc:title id="id">Harry Potter and the Philosopher's Stone</dc:title>
<meta name="calibre:series">Harry Potter</meta>
<meta name="calibre:series_index">1</meta>
```

```
<dc:title id="id">Harry Potter and the Chamber of Secrets</dc:title>
<meta property="belongs-to-collection" id="id-5">Harry Potter</meta>
<meta refines="#id-5" property="group-position">2</meta>
```

Here you can see the Harry Potter series, as coded above. Each book is an individual series, but because of the collection metadata, they are ordered and grouped together as "Harry Potter"
![collectionmetadata](collectionmetadata.webp "collectionmetadata")
