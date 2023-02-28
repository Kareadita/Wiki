---
title: Mylar
visible: true
taxonomy:
    category:
        - docs
        - filemanagement
---

! Note: This guide was written for Mylar3 v0.7.0

[Mylar](https://github.com/mylar3/mylar3) (aka Mylar3) is an automated Comic Book and Manga (cbr/cbz) management program. Kavita can watch and automatically import your Mylar managed files after setting up post processing to have the files tagged and renamed properly.

## Guide Overview

* [Setup](#setup)
* [Usage](#usage)

<hr style="border:5px solid #4ac694"> </hr>

## Setup

Completing the following will organize your media in Kavita according to [ComicVine](https://comicvine.gamespot.com/) where the volumes in are labeled as "Volume {VolumeYear}". This is the best option since some volumes don't have proper volume numbers setup which causes volumes to stack and not show properly in the Kavita library.

Access your Mylar instance from your web browser and complete the following:
1. Go to "Settings > Quality & Post Processing"
2. Under the "Post-Processing" section:
  * "Enable" Post-Processing
3. Under the "Metadata Tagging" section:
  1. "Enable" Metadata Tagging
  2. "Enable" Write ComicRack (cr) tags (ComicInfo.xml)
  3. "Enable" Overwrite existing cbz tags (if they exist)
  4. Click "Show Advanced" and
    1. "Enable" Tag Volume
    2. "Enable" Use Start Year as Volume
    3. Notes format: "CVDB"
4. Go to "Settings > Advanced Settings"
5. Under the "Renaming options" section:
  1. "Enable" Rename files
  2. Set "Folder Format" to `$Publisher/$Series ($Year)`
  3. Set "File Format" to `$Series $VolumeY $Annual #$Issue ($monthname $Year)`
  4. "Enable" Iss Number Padding"
  5. Set "Issue Number Padding Format" to `00x`
6. Under the "Miscellaneous" section:
  * "Enable" Place cover.jpg into Comic Directory for each comic
7. In Kavita, rescan your library and wait for changes to be applied. You may need to refresh the web page.

! Note: If a comic's title and volume year match, then they will still stack in Kavita. This situation may not exist, but just be aware of the possibility in case things still aren't showing properly in Kavita after setup.<br/>

<hr style="border:5px solid #4ac694"> </hr>

## Usage

To retag previously established comics in Mylar, after completing this setup section, complete the following:
1. In Mylar go to "Manage > Manage Comics"
2. Check the box for each comic you want to retag and in the dropdown menu on the upper left, select "MetaTag Series"
3. If that doesn't work, go to each commic and click "Manual MetaTagging"
