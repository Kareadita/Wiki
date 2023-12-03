---
title: Changelogs
---

Changelogs of all Kavita stable builds, which can also be found on [Github](https://github.com/Kareadita/Kavita/releases).



-------------------------

#### v0.3.7 - Stability 
Apr 6, 2021

This update is essentially 2 weeks of bugfixing and battle testing for existing Comics and Manga support. After these 2 weeks, I am positive this release is stable and can hold over anyone until the next release (v0.4 - book support). 

##### New
- More cover Image enhancements. Files with "cover" or "folder" are now taken before the first file
- Parsing enhancements that translate chapters with "b" suffix to ".5" ie) Chapter 202b -> Chapter 202.5
- Many performance enhancements to ensure the scan loop works faster and uses less memory. After initial scan, my test library of 230GB of manga takes 3 seconds to update new series.
- Library cards are now alphabetically sorted on Homepage
- Special grouping from last release has been refined and more specials are encapsulated, giving you ultimate control over reading order.
- MANY parsing enhancements/fixes to cover many new scenarios found in the wild
- Series reviews and summaries are now truncated by a read more button if they are longer than 250 characters
- Series reviews are much easier to make and edit
- When an archive cannot be read, we show a custom message and card design to inform the user
- On Connection Lost when user refreshes browser, we will try to go back to page they lost connection on

##### Fixed
- In Progress stream leaving old series due to abandoned rows being left in the DB
- In Progress stream was not ordered according to reading activity
- Don't allow specials to generate the series cover image (unless there are no better covers)
- Search doesn't show results when user searches with a localized name
- When changing the Name of a Series, it is being reset after a Scan Library
- Many areas weren't using a natural sort, so things like page 2, page 10 would cause page 10 to come first
- If a file was bound to a chapter, then extension changed, the file would stay with the chapter after a Scan Library, even though it's no longer on disk.
- Read vs Continue button wasn't showing correctly based on reading progress
- Go to Page (click the progress button) was off by 1
- Hitting Go to First page button would cycle through a virtual page split if the first page was a split page
- 2 split pages in a row would cause the second page to be shown as a normal page
- After updating a user library access, underlying page wouldn't show [Admin]
- Series' Summary and Reviews do not respect newline characters

-------------------------

#### v0.3.6 - Comic Book Support
Mar 28, 2021

I didn't think I'd release comic book support so soon, but it was easy to add and needed for my testers. You can now add a "Comic" library that will parse your comics and provide the same experience as your Manga.

Change log:
- Comic book support
- Lots of parsing fixes and enhancements for Manga
- Fixed scroll issue on context menu modal
- When server looses connection, try to put user back on original page from no-connection page.
- Enhanced the way we show "Specials" on series detail page. Now a "Specials" volume will show grouping all files that don't match. This will be enhanced in a future update. 

-------------------------

#### v0.3.5 - Linux now supported 
Mar 27, 2021

Due to some issues with paths, Linux users were unable to create a library. This and a few more bugs have been squashed in this release.

Change log:
- Date format on Volumes was showing incorrectly, removed as it's pointless (Last Modified) and replaced with Is Special designation.
- Changed all dates to be of format MM/dd/YYYY
- Fixed a bug with scrollbars in context modals
- Fixed a bug where Specials were showing twice
- First flow, ensure we go directly to library tab from "Create a library" link
- After a user registers for the first time, ensure we put them directly on login page
- Fixed directory picker not working consistently with windows and linux based paths.
- Fixed a bug where if a chapter had multiple archive files, they wouldn't all be extracted and thus you'd only be able to read up to the first archive. Now all are uncompressed and the reader will seamlessly switch between them. 

-------------------------

####  v0.3.2 - Hotfix
Mar 26, 2021

This hotfix is for linux/docker users where it was not possible to add a folder to a library due an extra / at beginning of the string.

-------------------------

#### v0.3.1 - Kavita v0.3.1 Hotfix
Mar 25, 2021

There was a major bug in Continue Reading button on the UI that has been fixed in this release. You can safety just copy the wwwroot folder from the release if you don't want to pull everything.

-------------------------

#### v0.3 - Kavita v0.3 - The "Main Driver" Release
Mar 24, 2021

With this release I can now ditch Ubooquity - my previous manga server of choice - with Kavita for all my reading needs. I would consider this as a full release with manga being it's primary focus over standard comic books. That being said, Kavita has a long road ahead filled with a host of new feature possibilities, like Book support, or proper metadata support. 

The change log is as follows (plus many other things I probably forgot):
- Image loading and Caching has been completely rewritten. Caching during manga reading is now super fast, you will forget you're reading over a network connection. Almost all images in the app are now lazy loaded with caching done by the browser
- Archive Support has been expanded to include RAR and many other various zipping formats thanks to using SharpCompress
- You can now access context menus from series detail page
- There is now pagination on series detail view, defaulting to 30 series per page
- ComicInfo.xml from within your archives will now populate the summary field on series during library scan
- You can now correct and fix matches on parsed series. e.g. Did Kavita think "One-Punch Man" was "One-Punch Men"? Correct it and future scans will ensure it parses as One-Punch Man
- You can now edit series metadata in the app + write your own review
- You can now search and navigate to any series from anywhere in the app
- Complete UX overhaul for better support on phone, tablet, or PC

-------------------------

#### v0.2 - Kavita v0.2
Feb 15, 2021

This was a fairly large release. This release originally was aimed at stabilizing and testing against a real library. During this, a ton of bugs were found that led to a complete rewrite to the DB structure and Scanning code. This helped Kavita have not only a more flexible structure, but improved matching and large speed ups. 

This release delivers the following:
- Stability & Bug fixes
- Ability to configure server settings 
- Ability to scheduler re-occurring Tasks
- Ability to mark a whole volume/chapter as read/unread
- Ability to reset user logins
- Ability to search library for items a user has access to
- Ability to log to file with rolling backups
- Ability to have user preferences reflect throughout app
- Ability to split full spread manga pages
- A full responsive pass-through on the app

Currently only building for Windows, create an issue if you want other OS builds. 

-------------------------

#### v0.1 - Kavita  v0.1
Jan 20, 2021

First release of Kavita. This release is more of a milestone than a proper release (although you can actually use server). This release allows for:
* User creation with Roles (admin/non-admin)
* Role based access to Libraries
* Segregation of Manga in different Libraries for whatever your needs
* Ability to rate manga
* Ability to track read progress
* Ability to read archive-based manga (cbz, cbr, zip)
* Ability to scan libraries ad-hoc
* Cache management
* Ability to read manga (no split page support)

While a lot was accomplished, a lot of the work is preliminary. This is the foundation for the next releases and polishing efforts. 

