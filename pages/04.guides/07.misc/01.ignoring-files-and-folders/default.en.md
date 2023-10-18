---
title: 'Special Keyword File/Folder Exclusion'
---

>>> This functionality only works on v0.5.6+. 

For advanced syntax please refer to the [library description](https://github.com/dazinator/DotNet.Glob/blob/develop/README.md#patterns)

## What is .kavitaignore
`.kavitaignore` is a file that lies at any point in the directory tree. It compiles a set of file patterns that matches the files that should be excluded from the scan.

## What is the basic syntax
* Blank lines are ignored.
* The `*` character is a wildcard.
* Patterns without the forward-slash ' /' character (e.g. `*.cbz`) match filenames in the same directory as the **.kavitaignore** file, or anywhere in the tree if **.kavitaignore** is a root of the section.
* Patterns with the forward-slash '/' character (e.g. `somedir/*`) match directory and file patterns relative to the directory containing the **.kavitaignore** file.

## Where and how many .kavitaignore files can be in my directory tree?
You can have a max of one file per directory in as many directories as you want.
A basic example of a file structure could be: (Basic syntax is shown. This is a basic showcase)
```
Library Root
  ┠── .kavitaignore							# Compiles global patterns to be applied to all subfolders. 
  ┠── Series Name
      ┠── .kavitaignore						# Compiles patterns to be applied to "Series Name". Could affect direct files and subfolders depending on the patterns inside of it
      ┠── Series Name v01.cbz
      ┠── Series Name v02.cbz
      ┠── Series Name v03.cbz
      ┖── Specials
        ┖── Series Name Omakes SP01.cbz
  ┖── Series Name 2
      ┠── .kavitaignore						# Each directory can have a .kavitaignore on it's own
      ┠── Series Name 2 Vol.01 Ch.1.cbz
      ┠── Series Name 2 Vol.01 Ch.2.cbz
      ⋮
      ┖── Series Name 2 Vol.02 Ch.6.cbz
```

## Example
If you only want EPUB files to show in a Kavita library (e.g. "Fiction Books"), create this `.kavitaignore` file inside the library folder:
```
#*.epub
*.mobi
*.azw
*.azw3
*.pdf
*.txt
*.cbz
*.cbr
*.zip
*.rar
*.opf
*.jpg
*.png
*.doc
*.docx
*.htm
*.html
```
