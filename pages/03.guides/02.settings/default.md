---
title: Settings
media_order: 'Default Page.PNG,Dark Mode On.PNG,Dark Mode Off.PNG,Bookmarks.PNG,Kavita new Admin page settings.PNG,CheckForUpdate.PNG,Changelog.PNG,Admin Dashboard.PNG'
admin:
    children_display_order: collection
---

#### Page overview
[General](#general-tab)<br/>
[User Management](#users-tab)<br/>
[Libraries](#libraries-tab)<br/>
[System](#system-tab)<br/>
[User Settings](#user-settings)<br/>
[Themes](#themes)<br/>


<hr style="border:5px solid #4ac694"> </hr>
## Admin Dashboard
### General Tab 
There are a multitude of settings that can be changed. The Port and Logging Level require a manual restart of the server to take effect. The cache directory is where temporary files will be placed, for example, when a user reads a file, the file is usually cached or the output of processing is placed in this directory. Kavita will clear this out regularly.

Allowing Anonymous Usage Collection is here, you can opt out. This setting allows you to send Anonymous data about your install which helps the Kavita team understand it's user base to make design decisions and performance enhancements. Some information that is collected is installId (helps us track how many installs we have), OS, version, if you are using docker or not and a few small pieces of data for features. None of the data can be tracked back to you. You can find the list [here](https://wiki.kavitareader.com/en/faq). The Stat collection is within the Kavita and KavitaStats repositories.

You can enable OPDS for your Server here. See this [page](https://wiki.kavitareader.com/en/guides/preferences/opds) for how it works.

Reoccurring tasks are also configurable to be changed.

<hr style="border:2px solid #4ac694"> </hr>
### Users Tab
From the Users Tab, admins can see the pending invites to their server and their active users. They can quickly see information around them and modify their password, delete the user, or edit their library access or roles. An admin cannot use this screen to modify their own roles (admin role will always have all applicable permissions) or library access (admin always has full access). An admin can use user settings page to change their own password.

![User%20Tab](User%20Tab.PNG "User%20Tab")

<hr style="border:2px solid #4ac694"> </hr>
### Libraries Tab
Adding and Editing Libraries is covered [here](https://wiki.kavitareader.com/en/guides/first-time-setup#adding-a-library-to-kavita).

<hr style="border:2px solid #4ac694"> </hr>
### System Tab
Under the System Tab admins can track what version Kavita is running, download logs, backup the database, check for updates, and manually Clear Cache. 
System Cache is cleared automatically upon Library Scan or as an system function each night.

!!! Note: Manually clearing system cache while other users are enjoying Kavita will incur a one-time loading during the reading experience.

![Kavita%20new%20Admin%20page%20settings](Kavita%20new%20Admin%20page%20settings.PNG "Kavita%20new%20Admin%20page%20settings")
Under the More Info section are links to Kavita related websites. [Donations ](https://opencollective.com/kavita)are very appreciated and directly support development and web hosting. If you need to report an issue please visit the [github](https://github.com/Kareadita/Kavita/issues) page. If Kavita is missing a function please visit the [Feature Request](https://feats.kavitareader.com/) link and make a new request, or vote on one you support.  

<hr style="border:2px solid #4ac694"> </hr>
#### Checking For Updates
Kavita offers a quick way to see if a new version is available. From the System tab, click Actions -> Check for Update. A modal will appear if an update is available where you can read the new features and fixes and click Download to open the Github and download the updated version. If you are are on Docker, there is no Download button. Please pull the latest image yourself. 

![CheckForUpdate](CheckForUpdate.PNG "CheckForUpdate")

In addition, a new tab is available: Changelog. You guessed it, it is a log of all the versions and the changes that go along with it. You can also jump to the Github to view it on the site itself. 

![Changelog](Changelog.PNG "Changelog")

<hr style="border:5px solid #4ac694"> </hr>
## User Settings
To access the user settings page, which holds the all settings for the logged in user, you can use the nav bar dropdown on your username and select "User Settings". These settings apply for the logged in user and will not affect any other user.

![Default%20Page](Default%20Page.PNG "Default%20Page")

<hr style="border:2px solid #4ac694"> </hr>
### Preferences
In this section, the user can configure site-wide preferences.
#### Dark mode
You can enable or disable dark mode


![UserSettingsDarkModeOn](Dark%20Mode%20On.PNG?classes=flex&resize=400,400)

![UserSettingsDarkModeOff](Dark%20Mode%20Off.PNG?classes=flex&resize=400,400)

#### Reading Settings
In the reading section, you will find all the options for the manga reader and the book reader. You can customize these as you like and they will apply on any of your devices. You can read more about each reader's setting [here (manga)](https://wiki.kavitareader.com/guides/webreader) and [here (book)](https://wiki.kavitareader.com/guides/bookreader).

#### Password
The logged in user can change their password from this screen.

<hr style="border:5px solid #4ac694"> </hr>
## 3rd Party clients
Kavita provides multiple ways to connect to your server from external applications. You can find them below:

[Generic (OPDS)](./opds)

[Tachiyomi](../misc/tachiyomi)
<hr style="border:5px solid #4ac694"> </hr>
## Themes
As of v0.5.2 Kavita allows for custom themes. We have opened up some elements to changes via css variables. Please read the Themes page below for further info:

[Themes](./themes)
