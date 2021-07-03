---
title: eBooks
---

### eBook Structure

eBooks are also parsed by filename and not by folder structure.

Kavita scans ebooks in a 2 pass process. First we try to parse from filename. If we can parse out **volume** and **series** name, then we treat it like a manga or comic.
If not enough information is present, then we use the internal epub metadata. Within that, we also look for certain tags to see if we can group them into a collection, like "Expanse".
Calibre eBook Managment software can be used to edit epub data to include Series, Volume, and Title so that books series parse correctly into the same series. [Calibre](https://calibre-ebook.com/)

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