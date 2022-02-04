---
title: Misc
media_order: 'Calibre Metadata.jpg,Kavita Calibre Bobiverse.jpg'
---

#### Page overview
Api Documentation<br/>
[Tachiyomi](./tachiyomi)<br/>

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

Edit your metadata making sure to set the Series and Number correctly so that Kavita groups the volumes of a Series together. 


<hr style="border:2px solid #4ac694"> </hr>
### Manga Manager
Currently in development. 
* Change covers for individual cbz (changes first image of the file)
* Rename files to include volume info

[Go to Manga Manager repo](https://github.com/ThePromidius/Manga-Manager)