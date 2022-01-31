---
title: 'First Time Setup'
---

#### Page overview
[General info](#general-info)<br/>
[Adding a library](#adding-a-library-to-kavita)<br/>
[//]: # (TO BE ADDED: Creating first admin account<br/>)


<hr style="border:4px solid #4ac694"> </hr>
### General Info
Kavita now supports mixed media libraries. For example your Light Novels (epub) and your Manga (cbz,cbr) can coexist in the same library. A library now is more just a grouping of media. Icons will show next to the series or book name to help you understand that, for example, one is a book and one is a PDF file.
![kavita%20Library%20File%20Type](kavita%20Library%20File%20Type.jpg "kavita Library Type")

<hr style="border:4px solid #4ac694"> </hr>
### Adding a Library to Kavita

To create a new Library an Admin can select the Server Settings option from the Drop Down menu.
![KavitaSettingsDropdown](KavitaSettingsDropdown.jpg "KavitaSettingsDropdown")
Then select the Libraries Tab.
![KavitaAdminLibraries](KavitaAdminLibraries.jpg "KavitaAdminLibraries")
Click the Add Library button. And give the Library a name.
![KavitaNewLibrary](KavitaNewLibrary.jpg "KavitaNewLibrary")
Once named click on the Type Drop Down menu to select the type of media in this Library.
![KavitaLibraryDropdown](KavitaLibraryDropdown.jpg "KavitaLibraryDropdown")
Next click the Plus sign icon to begin the Folder selection process. 
Each folder has a Share button which can be used to select all content in all sub-folders. However, Clicking on the folder names allows you to drill down further to Share the exact folder you want.
![KavitaDirectoryChoose](KavitaDirectoryChoose.jpg "KavitaDirectoryChoose")

! **Note**: The folder selection process is the same on any install but will depend heavily on your configuration. If a Docker install is used the bind mount for the shared Content will be in this list under that name. e.g. `-v /your/manga/directory:/manga` In this example /manga will be visible in the Folder selection process and will lead to your shared content.



