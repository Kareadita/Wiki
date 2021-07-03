---
title: eBooks
---

### eBook Structure

eBooks are also parsed by filename and not by folder structure.

Kavita scans ebooks in a 2 pass process. First pass tries to parse from filename. If **volume** and **series** name can be parsed, then it is treated like a manga or comic.
If not enough information is present, the internal epub metadata is used. Within the metadata, certain tags are used to group them into a collection, like "Expanse".
Calibre eBook Managment software can be used to edit epub metadata to include Series, Volume, and Title so that books series parse correctly into the same series. [Calibre](https://calibre-ebook.com/)

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