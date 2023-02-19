---
title: Misc
media_order: 'Calibre Metadata.jpg,Kavita Calibre Bobiverse.jpg'
taxonomy:
    category:
        - docs
---

<hr style="border:5px solid #4ac694"> </hr>

## Api Documentation

! v0.6.1.7+ no longer supports enabling swagger on Kavita installations. It can be used on dev builds or you can use our [API documentation](https://www.kavitareader.com/docs/api/#/).

### Pre-v0.6.1.6
To view the documentation you have to enable swagger in [settings](../02.settings/default.md) and head to `http://localhost:5000/swagger` or use [https://www.kavitareader.com/docs/api/#/](https://www.kavitareader.com/docs/api/#/)


Alternatively you can build Kavita on your local machine and then browse to the Swagger UI at [http://localhost:5000/swagger/](http://localhost:5000/swagger/). Kavita uses JWT for authentication, and thus you must attach your JWT key to Swagger to test against your local instance.

You can get your JWT by opening dev tools on a browser you have authenticated against and getting this key "kavita-user" from local storage. This will have a token key within it. Use "Bearer TOKEN_KEY" to authenticate. This must be on all APIs for Kavita to respond.

<hr style="border:3px solid #4ac694"> </hr>

## External tools

<hr style="border:3px solid #4ac694"> </hr>

Both MangaManager and ComicTagger work with comic files and manga files. They have different UI with different features
### ✯ Kavita recommends
#### Manga Manager
* Actively developed.
* Currently, only supports .cbz
* Extremely fast editings
* Bulk updates via GUI and CLI
* Allows for metadata scraping (currently limited to AniList and MangaUpdates, but more coming soon)
* Change covers and backcover (changes the first and last image of the file)
* Metadata editor with clear UI (allows bulk selection)
* Support for CLI usage
* Webp Converter
* Docker support for headless systems

[Go to MangaManager repo](https://github.com/ThePromidius/Manga-Manager)

<hr style="border:3px solid #4ac694"> </hr>

### Comic Tagger
* Import metadata from online metadata sources for comics (ComicVine only)
* Edit ComicInfo.xml for both cbz and cbr
* Option to bulk edit using CLI

[Go to comic tagger repo](https://github.com/comictagger/comictagger)


<hr style="border:2px solid #4ac694"> 

### Calibre
* EPUB metadata editor
* Can scrape from online and write Calibre-specific tags (which Kavita reads for grouping)
* Powerful but steep learning curve. Need to export books so opf file is written within the EPUB for Kavita to read properly. 
* [Site](https://calibre-ebook.com/es)

#### Calibre Metadata
Edit your metadata making sure to set the `Series` and `Number` correctly so that Kavita groups the volumes of a Series together. 
![Calibre%20Metadata](Calibre%20Metadata.jpg "Calibre%20Metadata")
![Kavita%20Calibre%20Bobiverse](Kavita%20Calibre%20Bobiverse.jpg "Kavita%20Calibre%20Bobiverse")

Then under Preferences change the Save to Disk settings to:
![Screenshot%202022-02-03%20162818](Screenshot%202022-02-03%20162818.jpg "Screenshot%202022-02-03%20162818")

Next, use the Save to Disk option and import those files into your Kavita library location.

<hr style="border:2px solid #4ac694"> 

### Sigil
* EPUB metadata editor which has tools to ensure the epub matches the spec (fixes corrupt epub metadata). 
* Supports a number of plugins to enhance experience
* [Site](https://sigil-ebook.com/)

### Komf
* Separate server that listens to Series Add events from Kavita and can scrape a number of configurable sources 
* Actively developed with support from the developer in Kavita discord
* Supports writing directly to Kavita's DB via the API or saving to ComicInfo.xml inside files.
* [Site](https://github.com/Snd-R/komf)

## External readers
These are only the guides for some of them. 

### OPDS

[Access the list of external readers here](https://wiki.kavitareader.com/en/faq/external-readers)

[Go to opds wiki page](../02.settings/01.opds)

<hr style="border:2px solid #4ac694"> </hr>

### Tachiyomi
[Access the guide for Tachiyomi here](./tachiyomi)

<hr style="border:2px solid #4ac694"> </hr>

### CDisplayEx
[Access the guide for CDisplayEx here](./cdisplayex)

<hr style="border:5px solid #4ac694"> </hr>
