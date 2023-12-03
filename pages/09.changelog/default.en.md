---
title: Changelogs
---

Changelogs of all Kavita stable builds, which can also be found on [Github](https://github.com/Kareadita/Kavita/releases).

-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### 
-------------------------
#### v0.4.3 - Webtoons, PDF, Mixed Media and a Wiki! 
Jul 25, 2021

v0.4.3 is out and it's action packed. What was supposed to be a small update for the dev team to get our build system in order turned out to deliver some huge wins for Kavita. 

First up is the new Webtoon Reader mode for Manga/Comic reading. This mode can be activated by clicking the reader mode in the menu. In webtoon mode, you scroll constantly through the pages. Like always, page progress is tracked and we deploy a custom buffing scheme to make it fast and performant, even on mobile devices. Some options in the reader are not applicable under the webtoon reader, like page splitting or fitting, so they will be disabled. 

Next up, mixed media libraries. Have you ever had your Light Novels and your Manga and wanted to have them in the same library? Well now that's possible. Going forward, a library is more just a grouping of media. You can have different media types (like epub and cbz) and they can sit next to each other in the same library. Icons will show next to the series name to help you understand that one is a book and one is an archive file. 

And lastly, we have PDF and raw image support. PDF support allows for you to read your PDFs within the manga/comic reader. We tried our hardest to provide a more book-like experience, however, PDF support is pretty limited for these functionalities. Raw image support is another new functionality where you can have loose leaf images that behave just like normal archives. There are some best practices to make the images easy to read, see the following:

```
└── Manga 2
    └── Vol. 1
        └── Ch.1 - Ch.3
            ├── 1.zip
            ├── 2.zip
            └── 3.zip
```

We also now have a [Wiki](https://wiki.kavitareader.com/), which is still a Work in Progress, but has a ton of information to help you with some questions and best practices. If you are interested in helping us build this out, drop us a line in our [discord](https://discord.com/invite/b52wT37kt7).

There is a ton more to this update, but before we get to it, I want to give a shout out of thanks to those who have donated to us, which are helping us pay for the hosting on our demo, our site, and our stats server. Thank you Allen Sampsell, Aleksey Gring, and H4v3n for your generous donations. The Kavita team appreciates it. 


##### Added
- Webtoon Reader mode is here. You can now read webtoons (or manga) by solely scrolling. Progress is kept and you can switch to/from it as a reading mode within the Manga Reader (#392)
- Added support for PDFs within Kavita. PDFs will open in the Manga reader and you can read through them as images. PDFs are heavier than archives, so they may take longer to open for reading. (#187)
- Raw Images (Manga/Comic) library types are here. They support loose leaf images within a folder. It is advisable to put a second folder named Volume 1 so the files group as one volume, otherwise they will all be separate specials, not fun. (#375)
- Added a server admin about tab with information about current version and links to discord, github, donations, etc (#391)
- Added iOS and Android icons when saving the page to your home screen (#356)
- Added Library-based action menu to the Library view. You can now scan from the library page without having to go back to dashboard (#363)
- Added Scan Series. From the series actionable menu, instead of scan library, which would kick off a filesystem scan on the library the series belonged to, instead we have "scan series" which will scan the folders represented by that series. If that series has files in the root of the library, the library root is scanned, but only said series files will be processed. This can make a refresh occur in under 500 ms (#371)
- (Parser) Added an alternative, folder-based parsing scheme that should help users with Comic or Ubooquity based naming. Can now also check for folder structure like the following (#313):
```
└── Manga 2
    └── Vol. 1
        └── Ch.1 - Ch.3
            ├── 1.zip
            ├── 2.zip
            └── 3.zip
```
- (Parser) Added parser cases for naming conventions FMD2 uses, including Vol.tbd (#361)
- (Stats) We are collecting a few new pieces of information for those that are allowing anonymous stat collection. We have added if you are on docker, if you are using the dark mode, and the number of cores. Please remember this data is anonymous and not tie-able back to you. You can inspect what we collect [here](https://github.com/Kareadita/KavitaStats/tree/main/Application/Domain/InstallationStatistics). (#407)
- (Accessibility) Nearly every page has had a title set for it (#422)
- Added a new button on admin dashboard to clear cache for the whole server (#428)
- Added Timeout for Regex matching to ensure malicious filenames don't crash system

##### Changed
- Major change in how Kavita libraries work. Kavita libraries will now allow for mixed media types, that means you can have raw images, archives, epubs, and pdfs all within your Manga library. In the case that the same Series exists between 2 different types of medias, they will be separated and an icon will show to help you identify the types. The correct reader will open regardless of what library you are on. Note: You  might have a lot of random series if you have images floating in your folders. (#416)
- Long running API requests like Mark as Read on a series card now disable the buttons until the request finishes (#381)
- When navigating to a url and being redirected to authenticate, Kavita will attempt to redirect after authentication to the original url
- Updated a few locations to redirect users back to library path instead of home, to prevent a back loop
- Refactored how downloading works on the UI side to use the backend's filename whenever possible, else provide a custom name (and use backend's extension) for bundled downloads. (#405)
- For Specials, Get Next/Prev Chapter should use the filename instead of arbitrary Number (which is always 0). Use the same sorting logic when requesting volumes on series detail, so sorting can happen in the backend. (#422)
- Moved the download logs to the new System page (#428)

##### Fixed
- Fixed a bug where certain titles could loose custom name overrides after a scan (#384)
- (Parser) Fixed a bad parsing case for "Series Name - Vol.01 Chapter 029 8 Years Ago" where somehow the chapter would parse as "029 8", thus making the file a special rather than chapter 29.
- When viewing a volume's files from a card's action menu, files were displayed in an arbitrary order instead of the reading order. This applied only for Specials and Raw Images. (#378)
- Fixed a bug with reading order when you have a volume file and chapter files bundled in one virtual volume, the continuous reader would not be able to navigate through them properly (#380)
- When server connection was lost and restored, the no connection page did not restore you to your previous page (#379)
- After creating a new user, the Last Active would show "01/01/0001" to denote never active, now "Never Active" will show (#376)
- (Manga Reader) Fixed an issue with Manga reader where every 7 pages a hard request would be made (and thus a loading indicator). Now pre-fetching works much better and loading indicators should almost never be seen. (#372)
- (Book Reader) Fixed an issue where Book Reader would not properly save the last position when a book didn't have a Table of Contents, even though it should regardless of Table of Contents (#360)
- (Book Reader) Fixed an issue where Book Reader wouldn't let you click on anchors in the page, when "Tap to Paginate" was on (#364)
- (Book Reader) Aligned the cover overlays for where to click for Tap to Paginate to the same colors as Manga Reader (#365)
- (Parser) Special Markers were taking series name parsed from filename which was unreliable. Instead, it will attempt to parse it from folder name (till library root). i.e) /manga/Hippos Attack/Specials/Artbook SP01.cbz -> Series name: Hippos Attack (#359)
- Fixed an issue where after adding a collection tag to a series, upon closing the modal, the underlying page didn't reflect the new changes (#393)
- Fixed an issue when the series detail thumbnail was too long it would push down the Volumes/Specials selection (#412)
- After adding a role to a user, ensure the screen updates immediately (#413)
- Fixed a bug where epubs would download as zip files instead of their native extension (this also applies to Manga/Comic libraries) (#399)
- Fixed an issue where checking if a file was modified since last scan always returned true, meaning we would do more I/O than was needed (#415)
- There wasn't enough spacing on the top menu bar on the Manga reader (#416)
- Fixed a bug where user preferences dark mode control always showed true, even if you were not using dark mode (#416)
- Fixed a bug where a forced metadata refresh wouldn't trigger a volume to force a refresh of cover image (#422)



-------------------------
#### v0.4.2 - Downloading and Redesigned Manga Reader! 
Jun 30, 2021

Welcome to v0.4.2! This release we saw 2 new developers join on and help in closing issues and building new features. This release also is home to a complete redesign of the Manga/Comic reader, the ability to download files from the UI, tons of parsing enhancements around specials and book grouping, and more user experience enhancements.

In addition to the action packed change log, we have added a new service to our mix. First, our website is now hosted at kavitareader.com instead of the previous github.io url. We now have KavitaStats, which is our way to collect anonymous install data to help us better understand our users. We collect important information like version of Kavita you run, types of files you use Kavita with, your OS, and your culture. There is no way to tie this data back to the end user. You can opt out under server settings.

We have a demo available! Want to try before you download? Then try out our demo. You can find the link and username/password on our [readme](https://github.com/Kareadita/Kavita).

We are now on [Open Collective](https://opencollective.com/kavita) if you want to sponsor or donate to the project. Open Collective allows for transparent accounting around where your money is going to. Donators will now show on the Readme. We appreciate any support.


##### Added
- Added a filter to the Directory to quickly filter folders and made the folder list scrollable rather than scrolling the whole body of the modal
- Added ability to change the port Kavita listens on from Admin page. Requires server restart to take effect.
- Added ability to change logging level from the Admin page. Requires server restart to take effect.
- Library type and number of folders shared is now visible on Manga Libraries page
- Ability to download your files! This role must be assigned to users, it is not enabled by default. Will automatically zip up if there are multiple files. Can download individual volume/chapters or whole series.
- Added a way to force Kavita to treat a file as a "Special" by using SP##, where # is a number in the filename. 
- Added rel="norefferrer" on all links within a user's epubs to prevent tracking
- Book Series grouping is now supported
  - Epub 3.2's can now use ```belongs-to-collection``` tag to group books into series [Spec](https://github.com/w3c/epub-specs/issues/1356)
  - Any Epub can use ```calibre:series_index, calibre:series, calibre:title_sort``` [Details](https://github.com/Kareadita/Kavita/issues/290)


##### Changed
- Specials on the UI are now sorted before being displayed
- Directory Picker will now let you share the current folder from any time in the picker flow
- Headings are now consistent between User Preferences and Admin screen
- Specials in the UI now hide the extensions
- Reworked how errors are handled within the app to hopefully reduce the amount of duplicate errors received
- Major rework on how book reader stores progress within a single page. With new method, it should work for any book. Resume to exact line you left off from any device. 
- Complete redesign of the Manga/Comic reader [View GIF](https://www.kavitareader.com/img/features/new-reader.gif)
  - Menu now opens in a bottom drawer and has a scroller to jump to pages, jump to first/last page, and jump between volume/chapters
  - Quick actions easily available to change reading direction, change reader mode, color tones, and access extended settings
  - Extended settings area for settings unlikely changed
  - Ability for menu drawer to auto close after 6 seconds. You can adjust within extended settings or on user settings page
  - Ability to apply extra darkness or a sepia tone to reduce blue light
  - New reader modes: Left/Right, Up/Down
  - Information about the volume/chapter you are reading is now showed in the top drawer
  - When applying reader modes or reading directions, the clickable areas will now show an overlay to help you understand where to click
  - Image scaling and Image splitting now show some contextual icons to help the user understand what they do
  - Close book button is now in the top drawer menu
- (Book Reader) Show current page and total pages on the progress bar in setting drawer
- Dark mode is the default for new users
-  .DS_Store and @eadir directories are completely skipped the Scanner
- Scanner will now pickup files without any numbers in them. This means files that couldn't previously be parsed will show up as a filename in your series.
- Removed "Anthology" as a keyword for treating a file as Special due to series having this word in their name.
- When debug log level, database parameters will be written to logger. This is not sensitive data and aids developers. 
- Redesigned Login Screen and Nav bar

##### Fixed
- Fixed an issue with Continuous Reading button not working correctly after manually updating a volume with multiple chapters as read/unread
- Fixed a bug on Directory Picker where pressing "Go Back" could result in being stuck not on Drive list 
- Dark mode theme is not persisting when logging out of app
- When marking a series as read/unread, the in progress activity stream does not update
- Continue reading button was broken on Firefox due to the way Firefox implemented a sort
- "Amazing Man Comics chapter 21" would parse series as "Amazing Man Comics chapter" and volume "21" 
- "Amazing Man Comics issue #21" would parse series as "Amazing Man Comics issue" and volume "21"
- Some archive files when opened for reading would be in a shuffled order resulting in bad reading order
- Fixed some inconsistencies in getting next/prev chapter item for Continuous Reader
- Fixed an unusual issue for arm versions of the docker container where files would fail if timestamp info wasn't copied over
-------------------------
####  v0.4.1.1 - Hotfix
Jun 7, 2021

There was a critical database exception that escaped testing and a hotfix had to be issued to fix it. 

##### Fixed
- Database update during Scan Library would fail due to a constraint issue with SeriesMetadata table
- An edge case for Continue Reading button was caught where after marking a volume with multiple chapters as read/unread, the calculation for continue reading button wouldn't be properly updated

**Please update.**
-------------------------
####  v0.4.1 - Collection Support
Jun 5, 2021

Collections are here! You can now tag your series with custom tags to group and explore them. A collection is a custom tag that can be applied to any series in Kavita. You can view all collection tags on the home page or by clicking the "Collections" header above the reel on home page. From there you can drill down and view all your collection tags.

If you need to quickly remove a few series from a collection tag, click the actions button on the collection tag and you can quickly use Edit action to modify multiple series at once. 

Collections don't have to just be for you. Do you have users? Want to promote a collection to all your users but keep some private to just you? Well you can do that. In that same edit action above, you can Promote a collection to be server-wide. All users can see the items with that collection (assuming they have access to those libraries), while the admin has complete control over what gets marked in it. 

**Note: There was a critical issue. The assets on this release have been updated.**

##### Added
- Collection support which allows admins to tag series and view them in a collection with cross library support. 
- Dark Mode! Each user can set their preference if they want to use Kavita with a custom dark theme. Persists across devices.
- Sentry Integration. Sentry is an error management platform to help the developers catch errors before it becomes a problem. All data is anonymized. 
- JWT Token Key Generation on startup. New users will not need to setup their own encryption key (but still can if they wish to)
- Added 7z, 7zip, and cb7 archive support
- We now build Raspberry Pi docker images
- (Book Reader) Added reading direction to the book reader, to keep feature parity with Manga reader
- (Book Reader) Scroll position is now saved (and resumed on any device) on books that have chapter markers on a single page (usually Light Novels)
- Recently Added and Collections pages from the carousel reel headers on home page

##### Fixed
- A multitude of issues around Continuous Manga next/previous chapters when there were multiple chapter files per virtual Volume. 
- Fixed an error when parsing a filename with Part, where Part was taken as Chapter despite Chapter being in the title (ie Tomogui Kyoushitsu - Chapter 006 Game 005 - Fingernails On Right Hand (Part 002).cbz)
- Fixed an issue around order in which chapters are inserted into the DB
- Rewrote Continue Reading button to work more consistently 
- MinimumNumberFromRange would throw an exception when non numeric characters would somehow get into the range field. Now the code will default to 0.0 whenever there is invalid data.
- Fixed a bug where archives with nested folders and folders of files with special characters would cause the end cached result to be skewed and the reading order would not be consistent
- Fixed an issue on Windows OS where once an epub was opened in Kavita, the file was locked to the Kavita process
- Fixed an issue where an admin changing the password for a user would cause the admin to be logged out and the password not changed
- Removed Webtoon as an option when creating libraries. It is handled by Manga already
- Some metadata keys get URI Encoded in epub html which led to failed lookups for anchor rewriting
- Scroll to Top button doesn't disappear when scroll is at the top
- Fixed a bug which when dark mode was activated or not, due to new system, the styles of the body would leak into the manga reader and background would not be black.
- Fixes an issue where btn-information in dark mode was unreadable
- Fixed an issue where if user came as null for some reason, a redirect to Login failed
- Fixed a bug where opening settings sidenav then navigating to a new page in book reader would push the side nav down
- Fixed an issue where carousel series card scan library would kick off the wrong library

##### Changed
- Password requirements have been changed to 6-32 characters length
- Increased the resolution of the Windows Icon
- Book Reader now handles style scoping @import statements
- When user becomes unauthenticated, quickly throw an exception to UI to inform them
- Library Backup label is now "Library Database Backup" in the Server Settings
- Changed Tabs on Series Detail to now be "smart". The tabs now auto-select based on the data.
- When using Continuous Reading on manga reader, the url will now update after you cross chapter boundary
- Section Title links on carousel reels now show an underline on hover/focus informing user they can click on it

-------------------------

####  v0.4 - Book Support
May 6, 2021

#####   Book support is finally here! 
Many users have been holding out to switch from Ubooquity until we had proper book support and that day is finally here. Internal testing users have already switched and loved some of the improvements over Ubooquity. In addition, this update brings even more stability to parsing and how we scan your disk. Some parallelization has been removed to reduce high I/O for the sake of speed (this will help any Pi users).

#####  How books work
Book support is currently limited to epub files only, mobi, pdf and other file formats are planned for a future release. Books will be parsed out based on both title and volume/chapter information. This allows us to have Light Novels mapped to multiple volumes, but other books, like Stephen King will be parsed out to their original title. Kavita does not enforce a strict folder grouping, you are free to keep all your Stephen King books in one folder, Kavita will map them out to separate entries. 

##### Book Reader
Out of the box, the book reader has a few cool functionalities. 
- We have font family overrides, line spacing, font size, and margin. 
- We have dark mode, which applies a darker color to the whole screen and darkens images in the book. Navigating between pages does not cause the dark mode to be reapplied. It is consistent for the reading session. 
- We have tap to paginate which lets you tap on the sides of the screen to paginate, like how the manga reader works
- We have a progress bar and go to page functionality like the manga reader (click the progress bar)
- Table of Contents is visible at any time from the side nav. When you click on any link in the application, it will keep that state in mind. So you can always back out via the "Go Back" button in the action bar. Go Back will scroll you back to where you were. 
- Links that are external will open in a new tab. 
- Like the manga reader, your book settings can be saved and applied to all books or overridden for the book you are reading.

#####  Future updates
In addition, this update will see a change in how releases are done. Instead of major releases every month or so, I will be splitting up features into minor release (v0.4.1, v0.4.2) with a new feature in each one. This will let me deliver faster and get feedback quicker. Join the discord to be apart of feedback and discussion of new features.

##### Added
- Book Support and an awesome Book Reader to go along with it
- Continuous Manga reading! The ability to move forward and back between different chapters/volumes seamlessly without leaving the manga reader. Please note, you will still incur the loading of the next volume when you transition.
- Swiper support to the library page so you can now drag the cards to see more
- Back to top button in the nav bar
- You can now press the "G" button to open the prompt to go to page (otherwise click the progress bar)
- Tap to Paginate (book reader) is now a user setting and can be turned on permanently in User Settings
- (Manga Reader) New Scaling Option: Automatic. This will try to choose the best fit for your device's screen size.
- RefreshMetadata action on series cards/series detail that will force a refresh of all metadata (cover images, summary) for just that series.
- Skip to content for book reader (accessibility)
- Series cards on the home page now show what library they are from and the library can be linked to see all series from said library
- First time readers of books or manga will now have a popup shown and the menu or sidenav will open automatically for them
- Documentation to the wiki explaining how to use the manga reader menu system
- Close button on the manga reader

##### Changed
- (Manga Reader) When changing the splitting options, the page re-renders instantly now.
- (Windows) Kavita icon is now packed so the EXE now has an icon when running
- Scaling default for Manga is now set to automatic by default. (new users only)
- Behind the scenes accessibility improvements for screen readers
- Search bar is now visible on small screen phone sizes
- Series info modals now show what library the series belongs to (admin only)

##### Fixed
- In Progress activity stream was not showing properly due to abandoned rows for progress after a series or volume was deleted during scan.
- Recently added was not respecting a user's access to libraries
- Home page, after marking a series as read/unread, the activity streams would show stale data. Data is now refreshed. 
- A LOT of book reader bugs during internal testing
- When creating a new account and password validation errors occur, UI wasn't showing them

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

