---
title: ebooks
---

### eBook Structure

eBooks are also parsed by filename and not by folder structure.

Kavita scans ebooks in a 2 pass process. First pass tries to parse from filename. If **volume** and **series** name can be parsed, then it is treated like a manga or comic.
If not enough information is present, the internal epub metadata is used. Within the metadata, certain tags are used to group them into a collection, like "Expanse".
Calibre eBook Managment software can be used to edit epub metadata to include Series, Volume, and Title so that books series parse correctly into the same series. [Calibre](https://calibre-ebook.com/)

Any EPUB can use:
```
If the following tags exist in an epub:
calibre:series_index
calibre:series
calibre:title_sort

Then map out the book as:

Series = calibre:series
Volume = calibre:series_index
Title = calibre:title_sort

An example of this would be:
Stephen King - Dark Tower 01 - The Gunslinger
Stephen King - Dark Tower 02 - The Drawing Of The Three

These belong to a series. In each epub, you'll see:
calibre:series = Dark Tower
calibre:title_sort = The Gunslinger, The Drawing Of The Three (respectively)
calibre:series_index = 1, 2 (respectively)
```
As of version 0.4.2, Kavita now supports EPUB version 3.2 "belongs-to-collection" tag as well.
```
<metadata>
    …
    <meta property="belongs-to-collection" id="c01">
        The Lord of the Rings
    </meta>
    <meta refines="#c01" property="collection-type">set</meta>
    <meta refines="#c01" property="group-position">2</meta>
    …
</metadata>
```

Here you can see the Harry Potter series, as coded above. Each book is an individual series, but because of the collection metadata, they are ordered and grouped together as "Harry Potter"
![collectionmetadata](collectionmetadata.PNG "collectionmetadata")
