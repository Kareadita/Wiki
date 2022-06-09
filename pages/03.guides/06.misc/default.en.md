---
title: Misc
media_order: 'Calibre Metadata.jpg,Kavita Calibre Bobiverse.jpg'
---

## Backup
If you are in need of restoring a backup, do not fret. It is incredibly easy. There are two ways to approach a backup. First, if you are seeing errors on an update to a new version, you can get an old version of your database from config/temp/version/kavita.db. This is a quick backup that occurs when database migrations are needed on an upgrade. You can just copy and paste this over your database in config/ and retry. 

If you however have some bad data and need to restore, then check config/backups for a zip of all user data. The scheduled backup (server settings) will save your database, appsettings.json, covers, themes, and bookmarks. You just need to copy and paste these over the config folder and restart. 

<hr style="border:5px solid #4ac694"> </hr>
## Misc information about Metadata
#### Publication Status
Kavita will can set the Publication Status on a series for you based on the underlying ComicInfo. If you have at least one ComicInfo with the `Count` property, then Kavita will at least mark the series as Ended. Kavita will also check if the number of Volumes or Chapters matches this exactly and if so, will mark the series as Completed. This logic will only run if the field is not locked. At any time you can hover over the tag badge in Series Detail to view how many issues or volumes you are missing. 

#### Format
Kavita will take the following Format tags from ComicInfo and use them to treat the file as a special:
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

<hr style="border:5px solid #4ac694"> </hr>
## Api Documentation
To view Kavita's API documentation, you will need to build Kavita on your local machine then browse to Swagger UI at http://localhost:5000/swagger/. Kavita uses JWT for authentication and thus you must attach your JWT key to Swagger to test against your local instance.

You can get your JWT by opening dev tools on a browser you have authenticated against and getting this key "kavita-user" from local storage. This will have a token key within it. Use "Bearer TOKEN_KEY" to authenticate. This must be on all APIs for Kavita to respond.

<hr style="border:5px solid #4ac694"> </hr>
## External readers
These are only the guides for some of them. 

[Access the list of external readers here](https://wiki.kavitareader.com/en/faq/external-readers)

<hr style="border:2px solid #4ac694"> </hr>
### Tachiyomi
[Access the guide for Tachiyomi here](./tachiyomi)

<hr style="border:5px solid #4ac694"> </hr>
## External tools

<hr style="border:2px solid #4ac694"> </hr>
### Comic Tagger
* Import metadata from online metadata sources for comics
* Edit ComicInfo.xml for both cbz and cbr
* Option to bulk edit using CLI

[Go to comic tagger repo](https://github.com/comictagger/comictagger)

<hr style="border:2px solid #4ac694"> </hr>
### Calibre
Lets you add metadata to ebooks.

[Go to calibre main page](https://calibre-ebook.com/es)
#### Calibre Metadata
Edit your metadata making sure to set the Series and Number correctly so that Kavita groups the volumes of a Series together. 
![Calibre%20Metadata](Calibre%20Metadata.jpg "Calibre%20Metadata")
![Kavita%20Calibre%20Bobiverse](Kavita%20Calibre%20Bobiverse.jpg "Kavita%20Calibre%20Bobiverse")

Then under Preferences change the Save to Disk settings to:
![Screenshot%202022-02-03%20162818](Screenshot%202022-02-03%20162818.jpg "Screenshot%202022-02-03%20162818")

Next use the Save to Disk option and import those files into your Kavita library location.

<hr style="border:2px solid #4ac694"> </hr>
### Manga Manager
Currently in development. 
* Change covers for individual cbz (changes first image of the file)
* Rename files to include volume info

[Go to Manga Manager repo](https://github.com/ThePromidius/Manga-Manager)