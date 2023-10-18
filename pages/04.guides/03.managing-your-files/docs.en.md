---
title: 'Managing your files'
taxonomy:
    category:
        - docs
    tag:
        - specials
        - metadata
metadata:
    'og:description': 'This page covers everything related to file management. This includes proper naming, local metadata, and how to update files in Kavita.'
    'og:title': 'Managing your files | Kavita Wiki'
    'og:url': 'https://wiki.kavitareader.com/en/guides-rework/managing-your-library'
admin: {  }
---

#### Page overview
- [Naming convention / File Structure](#naming-convention--file-structure)<br/>
  - [Specials](#specials)
  - [Volumes](#volumes)

 
<hr style="border:5px solid #4ac694">

# Naming convention / File Structure
It's important to know how Kavita parses the info from the files, so you can see what you want how you want.

Kavita uses parsing (not folder structure) to determine what is a series and what belongs to each series. Kavita requires that each series be in its folder and that no files are at root level of the library.

! Please Read [how the new scanner works](scanner/docs.en.md) prior to continuing with this article

!! **Important**: When parsing filenames, anything between parenthesis and parenthesis themselves will be removed from the series name. <br/>If you wish to separate series using `Series Name (2019)`, it's advised to change parenthesis to brackets `{` `}` and change series name in the UI

Folder and File Structure TOC:
* [Comic File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/comics)
* [Manga File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/manga)
* [eBooks File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/ebooks)
* [PDF File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/pdf)
* [Raw Images File Structure](https://wiki.kavitareader.com/en/guides/managing-your-files/raw-images)

For all types of libraries, Kavita has an override for treating files as Specials. 

[//]: # (TODO: Add more info related to specias)
## Specials

Kavita treats multiple types of files as "Specials" and will group them in a separate tab in series detail. Special marker (SP) will be removed from the UI title, however is used when ordering.

An entity is considered a special when a series can be parsed out of it, but no volume or chapter information is found:

```
Library Root
  ┖── Series Name
      ┖── Series Name.cbz
```
<hr style="border:1px solid #465176">
To force a Special status, the filename can include SP01, SP02, etc.
This will take the file and force it to be a special:

```
Library Root
  ┖── Series Name
      ┖── Series Name SP01 Special Name.cbz
```
<hr style="border:1px solid #465176">
Other keywords that are used to mark as special are `Specials`, `Omake`, `OneShot`, `Extra`, `Art Collection`, `Side Stories`:

```
Library Root
  ┖── Series Name
      ┖── Specials
          ┖── Series Name Omakes SP01.cbz
```
<hr style="border:1px solid #465176">
For it to identify as a special and not as the series from the filename, it will look up towards the library root and attempt to parse the series name from the folder names.<br/>
For example:

```
Library Root
  ┖── Again!!
      ┖── Specials
            ┖── Again The After Story SP01.cbz
```
Will parse `"Again!!"` for the Series name and group the file `"Again The After Story SP01.cbz"` as a special under the series `"Again!!"`
<hr style="border:1px solid #465176">

!!! Additionaly if the file is a `.cb*` file, you may set this value with the use of [ComicInfo metadata](#comicinfo) using the [format tag](#format)

! **Note**: Specials will fall back to the folder name for Series name. If you have a different name than the series files, then your special may not properly group.

<hr style="border:5px solid #4ac694">

## Volumes
In order for something to be parsed as having a volume, a volume must be on the filename.

Volume means:
* v1
* vol 1
* vol. 1
* volume 01
* Vol 7.5
* Volume.2000
* 卷2
* 册2
* 2巻
* t. 2
* tome 2
* 
!!! Additionaly if the file is a `.cb*` file, you may set this value with the use of [ComicInfo metadata](#comicinfo) using the `volume tag`
