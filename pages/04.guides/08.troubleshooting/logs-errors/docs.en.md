---
title: 'Common logs errors'
taxonomy:
    category:
        - docs
---

### There was an exception when opening epub book

The file is malformed. This message usually tells where is the issue. Reexporting with calibre usually helps

### ScannerService Some of the root folders for the library are empty

This error pops out when kavita scanner doesn't detect any files where it had already detected files.

This scan was aborted to avoid wiping user progress and series data if there is a mounting error.
### Incorrect EPUB navigation point: point ID is missing
The internal epub metadata is not pointing to the right files.

Try exporting the file with calibre or any tool that manages to fix the file metadata.