---
title: PDF
visible: true
---

### PDF
! This part of the wiki is in progress. If you have schemes that work, please raise a PR or reach out to Kavita team in discord. We would love to enhance our documentation.

Kavita supports PDF files out of the box, but due to a lack of standards around metadata, the support is limited to filenames and some hackery is needed to get things working correctly. 

There are a few different configurations that users have PDF files for: Table Top RPGs, One off books, and Magazines.

#### Table Top RGPs (TTRPGs)
The best way to organize TTRPG's is to use a folder name with .'s (if it is a name that would normally require spaces) such as DnD.5e or Pathfinder.2e. The PDF files themselves should have no numbers in the filename, and if numbers are required replace them with roman numerals. An example of this structure would look like this:

```
Library Root
  ┖── Pathfinder.2e
      ┠── Player's Handbook.pdf
      ┠── Bestiary I.pdf
      ┠── Bestiary II.pdf
      ┠── Bestiary III.pdf
```

And then inside Kavita itself you may rename the series from the folder name to the full name. The books will appear in the series entry in alphabetical order.

#### One-off Books
One off books are fairly simple to represent. Generally have the series name as the folder name and the book name as it is. Using SP markers will allow exact representation of the book's name by using the filename and will take the folder name as the Series. If no marker used, the Library type is used for parsing. Book defaults to Manga, Comic uses Comic parsing rules.

#### Magazines
Magazines are very tricky due to an utter lack of coherence in the naming conventions when collecting. Magazines might be used the same way as TTRPGs with the special marker. Users may want to collect different years as individual volumes or keep them all separated. 

! We need your help with setups. Please reach our or submit a PR. 
