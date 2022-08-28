---
title: 'Special Keyword File/Folder Exclusion'
---

! This page is WIP and is part of the v0.5.6 release. 

# Special Keyword File/Folder Exclusion
Kavita by default will exclude unsupported file types and single `cover.jpg` files in folders. 

! Note: If the files were scanned before excluding them in `.kavitaignore`, they won't get updated unless the files themselves change. 

### Excluding New Content with .kavitaignore
! Warning: This is an advanced feature and not intended for general users
The file syntax is the following:
- One line per ignored rule
- Blank lines are ignored.
- The * character is a wildcard.
- Patterns without the forward-slash (/) character (e.g. `*.cbz`) match filenames in the same directory as the `.kavitaignore` file, or anywhere in the tree if `.kavitaignore` is a root of the section.
    ```
    Root:
    	.kavitaignore
        some_file.cbz (ignored)
        some_folder
        	some_file.cbz (not ignored)
            ```
- Patterns with the forward-slash (/) character (e.g. somedir/*) match directory and file patterns relative to the directory containing the `.kavitaignore` file.
 ```
    Root:
    	.kavitaignore
        some_file.cbz ( not ignored)
        some_folder
        	some_file.cbz (ignored)
            ```

### Examples
```
# Ignore all files with "" in the name
*trailer*

# Ignore files with the extension ".cr2"
*.cr2

# Ignore directories called "Modified"
*Modified/*

# Ignore all ".tif" files in the "thumbnails" subdirectory
*thumbnails/*.tif