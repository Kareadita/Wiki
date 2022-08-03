---
title: FAQ
admin:
    children_display_order: collection
---

Frequently Asked Questions

* Q. **I really like Kavita, but can it mirror or just use my folder structure?** 
* A. No, Kavita uses filenames for parsing and is not designed to use folder structure. Please don't ask for this feature, it will never be implemented. If this is important to you, [Ubooquity](https://vaemendis.net/ubooquity/) may be a better choice, as it offers this feature. 

===

* Q. **I started Kavita but get Access Denied?** 
* A. Kavita needs to be executable and the directory it is installed in must be writable by Kavita. On Linux, `chmod +x ./Kavita` is usually sufficient. On Windows, ensure you did not install it in `Program Files` or `Program Files (x86)`.

===

* Q. **Kavita doesn't seem to run on my computer?**
* A. Kavita will not run on any processor (CPU) that does not support AVX flag/options. Generally, Core i3/i5/i7/i9 support them, whereas Pentium and Celeron CPUs do not. CPUs from 2011 onwards should support AVX.

===

* Q. **Can I use Kavita with a Google Drive mount?**
* A. Yes, you can use Plexdrive or rclone. Although it is not officially supported.
Rclone requires a specific configuration to cache files locally and work better with Kavita. Here is a user-provided configuration that works well:
```
rclone mount [your mount name]: [local path to be mounted] \
    --no-checksum \
    --use-server-modtime \
    --no-gzip-encoding \
    --no-seek \
    --allow-other \
    --allow-non-empty \
    --cache-read-retries 15 \
    --cache-db-purge \
    --buffer-size 512M \
    --dir-cache-time 500h \
    --timeout 500h \
    --vfs-cache-max-age 500h \
    --vfs-read-ahead 1G \
    --vfs-read-chunk-size 32M \
    --vfs-cache-max-size 25G \
    --cache-dir=[your folder path here] \
    --vfs-cache-poll-interval 10s \
    --poll-interval 10s \
    --attr-timeout 20s \
    --vfs-cache-mode full
```

===

* Q. **Does Kavita collect any data on me?**
* A. By default, Kavita will collect stats on your installation. You can opt out at any time by turning off "Send Data" from the Admin Dashboard. All data is anonymized and contains no information about your filenames or IP. The Kavita team actively uses this data to help design the UX and plan enhancements. If you chose to remain opted-in, thank you. It really helps in the design and planning effort. You can view the code at any time [here](https://github.com/Kareadita/KavitaStats). Here is a [record](https://github.com/Kareadita/KavitaStats/blob/main/KavitaStats/Entities/StatRecord.cs) from our stats database:
```
{
    "InstallId":"0cf3ad15",
    "LastUpdate":"2021-08-21T00:00:11.385Z",
    "Os":"Linux 5.4.0-80-generic #90~18.04.1-Ubuntu SMP Tue Jul 13 19:40:02 UTC 2021",
    "KavitaVersion":"0.4.3.39",
    "DotNetVersion":"5.0.9",
    "IsDocker":true,
    "NumOfCores":4,
    "HasBookmarks" true,
    "NumberOfLibraries": 4,
    "NumberOfReadingLIsts": 2,
    "NumberOfCollections": 0,
    "TotalFiles": 10351
    "ActiveTheme": "Dark",
    "ReadingMode": "Webtoon"
}
```

===

* Q. **Is there a way to use Kavita without Authentication?**
* A. No, this type of functionality is not supported and there are no plans. Kavita offers Refresh Tokens which should keep you authenticated without having to manually log in. 

===

* Q. **Is there a way to see what isn't being added to Kavita during a scan?**
* A. As of now, there is no dedicated UI page. You can instead search the logs for this:
```
There are multiple series that map to normalized key SERIESNAME. You can manually delete the entity via UI and rescan to fix it. This will be skipped
```

===

* Q. **Follow up, some of my epubs aren't being added, how come?**
* A. If an epub isn't being added, it is likely due to a malformed file/metadata. Search for `[BookService] There was an exception when opening epub book:` in your logs to validate. You can use Calibre to reexport, which usually fixes the malformed metadata.

===

* Q. **Sometimes I add ComicInfo to the first archive, but Kavita doesn't show it at a series level. Is this a bug?**
* A. There are 2 things to keep in mind. If the underlying file Created/LastModified isn't being changed since our last scan, we skip it to save on time and resources. In addition, if the file is not an archive starting with C, like cbz, cbr, etc, then it will not be checked for ComicInfo metadata. 

===

* Q. **I have a Pi (Buster) that doesn't run Kavita in Docker. Is there a workaround?**
* A. There is a bug in the OS version for Buster. We have a workaround. You can run the docker container with privileged. See: [https://github.com/Kareadita/Kavita/issues/821](https://github.com/Kareadita/Kavita/issues/821)

===

* Q. **v0.5.1 Introduced Email functionality, how does it work?**
* A. The email functionality only works for servers that are publicly accessible from the web. For example, if you access your server on localhost or an internal IP, the email code will never execute. However, you still need to have an email confirmed. Since emails won't send, all email flows will write the link to your logs. This is the best way for you to confirm your email when doing the one-time migration or setting up accounts for your users. You do not need to have a valid email unless you plan to use the forgot password function. You can set up your users' accounts for them by doing the invite flow and using their invite link. We do not collect any email account information. It is deleted immediately after being dispatched by an automatic rule. You can run your own email service as well. 

===

- Q. **I'm seeing duplicate chapters/issues. What's going on?**
- A. This may happen if you've been a longtime user. Over the version iterations, the DB has changed pretty significantly. There are two options. In either case, **Backup your Database first**:
    - 1. You can choose to start fresh, delete your current database and reconfigure the instance. This is not recommended or ideal.
    - 2. You can use execute the following SQL commands on your DB using some tool like DB Browser.
```
// Verify Duplicates
SELECT b.* FROM MangaFile b JOIN( 
    SELECT *, MIN(Id) as low_ID, Count(*) FROM MangaFile
    GROUP BY FilePath
    HAVING COUNT(*) > 1 ) c
ON b.FilePath = c.FilePath
WHERE b.Id != c.low_ID
ORDER BY b.FilePath
```
```
// Delete Chapter Information first
DELETE FROM Chapter 
WHERE Id IN (
    SELECT b.ChapterId FROM MangaFile b JOIN( 
        SELECT *, MIN(Id) as low_ID, Count(*) FROM MangaFile
        GROUP BY FilePath
        HAVING COUNT(*) > 1 ) c
    ON b.FilePath = c.FilePath
    WHERE b.Id != c.low_ID
    ORDER BY b.FilePath
)
```
```
// Delete MangaFile Information
DELETE FROM MangaFile
WHERE Id IN (
    SELECT b.Id FROM MangaFile b JOIN( 
        SELECT *, MIN(Id) as low_ID, Count(*) FROM MangaFile
        GROUP BY FilePath
        HAVING COUNT(*) > 1 ) c
    ON b.FilePath = c.FilePath
    WHERE b.Id != c.low_ID
    ORDER BY b.FilePath
)
```

===

- Q. **How exactly does Estimated Reading Time work?**
- A. Kavita calculates the reading time using two different methods. The calculated reading time may not always reflect the actual reading time, but should be sufficient in providing a general sense of how long it will take to read or finish off a series.
  - For items where we can count words (epub), we use a spread of 10,260 to 30,000 words per hour to calculate min, max, and average. 
  - For files that don't have countable words, we use a spread of 2.75 to 3.33 minutes per page. This works in most cases but might fail for files like pdfs, for which we still use images on the backend, or webtoons, which have a long strip format.

FAQ Pages TOC:

[External Readers](https://wiki.kavitareader.com/faq/external-readers)

[Compare to Competition](https://wiki.kavitareader.com/faq/compare-to-competition)