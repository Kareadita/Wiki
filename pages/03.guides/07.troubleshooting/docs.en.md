---
title: 'Troubleshooting kavita'
taxonomy:
    category:
        - docs
---

>>> This page is currently being build and it content might change without prior notice

In this section of the wiki, common errors will be layed out and will be walked through to fix them.

Check [logs-errors](logs-errors) section to learn more about a log error.

## Something is not working right. What to do?


Please follow the following generic steps to troubleshoot your issue.
### 1. Is my folder structure compliant with scanner requirements?
As of v.0.5.6 file structure changed due to the scanner update please do read [how the new Scanner works](/guides/managing-your-files/scanner)

TLDR:
- Loose files can't be at the root of the library.
- Kavita expects all series to be nested in it's own folder.**
- Having multiple series in one folder is not supported but does work.
- For series scan, if the series folder is no longer on the disk, the scan will be aborted. A library scan should be run which will delete the series.
- Not every action you can perform on a folder will change its modification time, including renaming and moving it. Keep this in mind if library scans are not working as expected. Do a series scan instead.
** Does not apply for epub files

### My folder structure is compliant with new requirements
If you are sure your files are compliant, then something is going on. Put your logging level on Debug and redo process.

After that check the logs and take a look at [logs-errors](logs-errors) section.

### My files are not being grouped correctly. What to do?
Ensure you understand that pdfs, epubs and cb* do not stack in Kavita. Kavita separates by format and series name due to different format having different readers

	