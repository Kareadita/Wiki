---
title: FAQ
admin:
    children_display_order: collection
---

Frequently Asked Questions

* Q. **I started Kavita but get Access Denied?** 
* A. Kavita needs to be executable and the directory it is installed in must be writable by Kavita. On linux, chmod +x ./Kavita is usually sufficient. On Windows, ensure you did not install it in Program Files or Program Files (x86)

* Q. **Kavita doesn't seem to run on my computer?**
* A. Kavita will not run on any processor (CPU) that does not support AVX flag/options. Generally, Core i3/i5/i7/i9 support them, whereas Pentium and Celeron CPUs do not. 2011 and after CPUs should support AVX.

* Q. **Can I use Kavita with a Google Drive mount?**
* A. Yes, you can use Plexdrive or rclone. Although it is not Officially supported.
Rclone requires some specific configuration to cache files locally, and work better with Kavita. Here is a user-provided configuration that works well:
```
rclone mount \
    --allow-other \
    --buffer-size 256M \
    --dir-cache-time 720h \
    --vfs-read-ahead 512M \
    --vfs-read-chunk-size 16M \
    --vfs-cache-mode full
```

* Q. **Does Kavita collect any data on me?**
* A. Kavita by default will collect stats on your install, this can be turned off after the initial launch. All data is anonymized and contains no information about your filenames or IP. We actively use this data to help design the UX and plan enhancements. Here is a record from our stats database:
```
{
   "_id":{
      "$binary":"uRYzM8KNRh+emq1wAQuq9Q==",
      "$type":"4"
   },
   "InstallId":"0cf3ad15",
   "LastUpdate":{
      "$date":"2021-08-21T00:00:11.385Z"
   },
   "UsageInfo":{
      "UsersCount":5,
      "FileTypes":[
         ".epub",
         ".cbz",
         ".cbr",
         ".zip",
         ".jpg",
         ".pdf"
      ],
      "LibraryTypesCreated":[
         {
            "Count":1,
            "Type":0
         },
         {
            "Count":1,
            "Type":1
         },
         {
            "Count":2,
            "Type":2
         }
      ]
   },
   "ServerInfo":{
      "Os":"Linux 5.4.0-80-generic #90~18.04.1-Ubuntu SMP Tue Jul 13 19:40:02 UTC 2021",
      "Culture":"",
      "BuildBranch":"Release",
      "KavitaVersion":"0.4.3.39",
      "DotNetVersion":"5.0.9",
      "RunTimeVersion":".NET 5.0.9",
      "IsDocker":true,
      "NumOfCores":4
   },
   "ClientsInfo":[
      {
         "ScreenResolution":"414 x 896",
         "KavitaUiVersion":"0.4.2",
         "CollectedAt":{
            "$date":"2021-08-20T02:14:25.655Z"
         },
         "PlatformType":"mobile",
         "Browser":{
            "Name":"Safari",
            "Version":"14.1.2"
         },
         "Os":{
            "Name":"iOS",
            "Version":"14.7.1"
         },
         "UsingDarkTheme":true
      }
   ]
}
```

* Q. **I can't read PDF files**
* A. Kavita currently does support PDF files on Raspberry Pi devices (ARM-based architecture), however users may need to manually install a dependencies `libgdiplus`. We are currently investigating a way to do this for you. 

* Q. **Is there a way to use Kavita without Authentication?**
* A. As of v0.4.7, Kavita supports disabling Authentication. All admin accounts will still require a password, however, a user chooser will be available to login via. No password is required to be filled out. This can be undone and the password will be presented to you to for all users. 

* Q. **Is there a way to see what isn't being added to Kavita during a scan?**
* A. As of now, there is no dedicated UI page. You can instead search the logs for this:
```
There are multiple series that map to normalized key SERIESNAME. You can manually delete the entity via UI and rescan to fix it. This will be skipped
```
* Q. **Follow up, some of my epubs aren't being added, how come?**
* A. If an epub isn't being added, it is likely due to a malformed file/metadata. Search for `[BookService] There was an exception when opening epub book:` in your logs to validate. 

FAQ Pages TOC:

[Folder and File Structure](https://wiki.kavitareader.com/faq/folders-and-file-structure)

[Compare to Competition](https://wiki.kavitareader.com/faq/compare-to-competition)