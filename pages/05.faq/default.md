---
title: FAQ
admin:
    children_display_order: collection
---

Frequently Asked Questions

* Q. **I really like Kavita, but can it mirror or just use my folder structure?** 
* A. No, Kavita uses filenames for parsing and is not designed for using folder structure. Please don't ask for this feature, it will never be implemented. If this is important to you, Ubooquity can be used and delivers this experience. 

* Q. **I started Kavita but get Access Denied?** 
* A. Kavita needs to be executable and the directory it is installed in must be writable by Kavita. On linux, chmod +x ./Kavita is usually sufficient. On Windows, ensure you did not install it in Program Files or Program Files (x86)

* Q. **Kavita doesn't seem to run on my computer?**
* A. Kavita will not run on any processor (CPU) that does not support AVX flag/options. Generally, Core i3/i5/i7/i9 support them, whereas Pentium and Celeron CPUs do not. 2011 and after CPUs should support AVX.

* Q. **Can I use Kavita with a Google Drive mount?**
* A. Yes, you can use Plexdrive or rclone. Although it is not Officially supported.
Rclone requires some specific configuration to cache files locally, and work better with Kavita. Here is a user-provided configuration that works well:
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

* Q. **Does Kavita collect any data on me?**
* A. Kavita by default will collect stats on your install, this can be turned off after the initial launch. All data is anonymized and contains no information about your filenames or IP. We actively use this data to help design the UX and plan enhancements. You can view the code at any time [here](https://github.com/Kareadita/KavitaStats) Here is a [record](https://github.com/Kareadita/KavitaStats/blob/main/KavitaStats/Entities/StatRecord.cs) from our stats database:
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
     "NumberOfLibraries": 4
}
```

* Q. **Is there a way to use Kavita without Authentication?**
* A. No, this type of functionality is not supported and there are no plans. Kavita offers Refresh Tokens which should keep you authenticated without having to manually login. 

* Q. **Is there a way to see what isn't being added to Kavita during a scan?**
* A. As of now, there is no dedicated UI page. You can instead search the logs for this:
```
There are multiple series that map to normalized key SERIESNAME. You can manually delete the entity via UI and rescan to fix it. This will be skipped
```
* Q. **Follow up, some of my epubs aren't being added, how come?**
* A. If an epub isn't being added, it is likely due to a malformed file/metadata. Search for `[BookService] There was an exception when opening epub book:` in your logs to validate. 

* Q. **I have a Pi (Buster) that doesn't run Kavita in Docker. Is there a workaround?**
* A. There is a bug in the OS version for Buster. We have a workaround. You can run the docker container with privileged. See: https://github.com/Kareadita/Kavita/issues/821


FAQ Pages TOC:

[Folder and File Structure](https://wiki.kavitareader.com/faq/folders-and-file-structure)

[Compare to Competition](https://wiki.kavitareader.com/faq/compare-to-competition)