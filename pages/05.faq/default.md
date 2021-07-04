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

*Q. Can I use Kavita with a Google Drive mount?
*A. Yes, you can use Plexdrive or rclone. Although it is not Officially supported.
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

FAQ Pages TOC:

[Folder and File Structure](https://wiki.kavitareader.com/faq/folders-and-file-structure)