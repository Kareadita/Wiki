---
title: 'Compare to Competition'
---

# Comparsion
This page may be out of date as all software except Ubooquity is in active development. To provide a quick summary: 
* Komga is more focused on Comics and management of your comics (including reading), it does not support reading any text-based documents as text (aka epubs are read as images). Great software, alternative UX, active development. 
* Calibre-web is a nicer frontend to Calibre. You need to have Calibre manage your files. I don't personally use this, but the UX is much nicer than the actual Calibre application. Very focused on ebooks.
* Ubooquity is known by all. Maps your folders into cards and provides a basic reader for cbz/cbr and pdf (as images). No longer developed.
* Mango: I've never used it, but I think it has a downloader and that's pretty cool.
* Kavita: Focused on the reading experience and exploring your collection. Epub and pdf readers allow for text and are feature rich. Uses metadata and filename parsing to group into series, volumes, etc.  

| | [Kavita](https://github.com/Kareadita/Kavita) | [Mango](https://github.com/hkalexling/Mango) | [Komga](https://github.com/gotson/komga) | [Ubooquity](https://vaemendis.net/ubooquity/) | [Calibre-web](https://github.com/janeczku/calibre-web) |
|  ------ | ------ | ------ | ------ | ------ | ------ |
| Multi-User Support | ✓ | ✓ | ✓ | ✓ | ✓ |
| Download |Individual file, volume, or entire series | ✗ | Individual files | Individual files | Individual files |
| Role-based Security| ✓ | | ✓ |  | ✓ | 
| OPDS  | ✓* | ✓* | ✓* | ✓ | ✓ |
| Dark/light mode | ✓ | ✓ | ✓ | Not out of the box | ✗ |
| Formats | cbr, cbz, cb7, cbt, zip, rar, tar.gz, 7zip, 7z, epub, pdf, png, jpg, jpeg, webp | cbz, cbr, zip, rar | cbz, cbr, pdf, epub*** | cbz, cbr, pdf, epub | mobi, epub, pdf, cbz, cbr, cbt, lit, doc(x), odt, rtf, html |
| Reading Progress | ✓ | ✓ | ✓ | ✓ | ✓ |
| Metadata | ✓++ | ✓ | ✓++ | ✗ | ✓ |
| Cross Platform | ✓ | ✓ | ✓ | ✓ | ✓ |
| Accessibility and Screen Reader Support | ✓ | | ✗ | | ✗ |
| Webtoon/Continuous Scroll | ✓ | |✓ | | |

* *= OPDS-PS support

* ***= epub support is limited to images only 

* += Currently partial metadata is pulled from epub OPF and ComicInfo.xml. Planned is extended pulling and pulling from online Sources. 
* ++= Supports pulling metadata from epub OPF and ComicInfo.xml

! **Note**: No software supports RAR5 at this time.

!!! **Note**: Kavita follows [Web Content Accessibility Guidelines](https://www.w3.org/TR/WCAG21/) (WCAG) 2.1 to support readers with disabilities.