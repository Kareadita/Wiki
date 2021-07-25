---
title: Settings
media_order: 'Admin Dashboard.PNG,Default Page.PNG,Dark Mode On.PNG,Dark Mode Off.PNG,Kavita new Admin page settings.jpg'
---

Kavita offers a few different settings for you as an owner and for users. 

# Server Settings
To access the admin dashboard, which holds the all settings for the server, you can use the nav bar dropdown on your username and select "Server Settings". This option is only available for admins.

![Admin%20Dashboard](Admin%20Dashboard.PNG "Admin%20Dashboard")

### General Tab 
There are a multitude of settings that can be changed. The Port and Logging Level require a manual restart of the server to take effect. The cache directory is where temporary files will be placed, for example, when a user reads a file, the file is usually cached or the output of processing is placed in this directory. Kavita will clear this out regularly.

Allowing Anonymous Usage Collection is here, you can opt out. This setting allows you to send Anonymous data about your install which helps the Kavita team understand it's user base to make design decisions and performance enhancements. Some information that is collected is file types within kavita, number of users, screen sizes and browser information, OS, version, if you are using docker or not. The Stat collection is within the Kavita and KavitaStats repositories.

Reoccurring tasks are also configurable to be changed.
### Users Tab
Adding Users is covered [here](https://wiki.kavitareader.com/guides/user-management).

### Libraries Tab
Adding and Editing Libraries is covered [here](https://wiki.kavitareader.com/guides/adding-a-library).

### System Tab
Under the System Tab admins can track what version Kavita is running. Download Logs, and manually Clear Cache. 
System Cache is cleared automatically upon Library Scan or as an system function each night.

!!! Note: Manually clearing system cache while other users are enjoying Kavita will trigger another background cache event.

![Kavita%20new%20Admin%20page%20settings](Kavita%20new%20Admin%20page%20settings.jpg "Kavita%20new%20Admin%20page%20settings")
Under the More Info section are links to Kavita related websites. Donations are very appreciated and directly support development and web hosting. If Kavita is missing a function please visit the Featurehub link and make a new request, or vote on one you support.  

# User Settings
To access the user settings page, which holds the all settings for the logged in user, you can use the nav bar dropdown on your username and select "User Settings". These settings apply for the logged in user and will not affect any other user.

![Default%20Page](Default%20Page.PNG "Default%20Page")

### Site Settings
In this section, the user can configure site-wide settings. For now, there is only Dark Mode. Dark Mode is the default theme (v0.4.2+).


![UserSettingsDarkModeOn](Dark%20Mode%20On.PNG?classes=flex&resize=600,600)
![UserSettingsDarkModeOff](Dark%20Mode%20Off.PNG?classes=flex&resize=600,600)

### Reading Settings
In the reading section, you will find all the options for the manga reader and the book reader. You can customize these as you like and they will apply on any of your devices. You can read more about each reader's setting [here (manga)](https://wiki.kavitareader.com/guides/webreader) and [here (book)](https://wiki.kavitareader.com/guides/bookreader).

### Password
The logged in user can change their password from this screen.

### System Tab