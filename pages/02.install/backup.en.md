## Backup
If you need to restore a backup, do not fret. It is incredibly easy. 

There are two ways to approach a backup. 

First, if you are seeing errors on an update to a new version, you can get an old version of your database from `config/temp/version/kavita.db` This is a quick backup that occurs when database migrations are needed on an upgrade. You can just copy and paste this over your database in config/ and retry. 

If you however have some bad data and need to restore, then check `config/backups` for a zip of all user data. The scheduled backup (server settings) will save your database, appsettings.json, covers, themes, and bookmarks. You just need to copy and paste these over the config folder and restart. 
