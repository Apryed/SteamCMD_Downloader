# SteamCMD_Downloader
Download SteamCMD Apps with Ease

# How to Use?
Download "[DownloadApp.ps1](../../releases/latest/download/DownloadApp.ps1)" and place it next to SteamCMD.exe - [SteamCMD download here](https://developer.valvesoftware.com/wiki/SteamCMD).
Create a file called "[MyAppList.json](https://raw.githubusercontent.com/Apryed/SteamCMD_Downloader/main/MyAppList.json)" with the follow format:


```
[
	{
		"Name":"",
		"AppID":"",
		"Beta":[]
	}
]
```
If more entries needed, just add:
```
	,{
		"Name":"",
		"AppID":"",
		"Beta":[]
	}
```
after last `}` used.

Example:
```
[
	{
		"Name":"CS2",
		"AppID":"740",
		"Beta":[]
	},
	{
		"Name":"L4D2",
		"AppID":"222860",
		"Beta":[]
	},
	{
		"Name":"7 Days to Die",
		"AppID":"294420",
		"Beta":["alpha8.8","alpha9.3","alpha10.4","alpha11.6","alpha12.5","alpha13.8","alpha14.7","alpha15.2","alpha16.4","alpha17.4","alpha18.4","alpha19.6","alpha20.7","alpha21.0","alpha21.1","alpha21.2","latest_experimental","v1.0"]
	}
]
```
AppID can be found in [SteamDB](https://steamdb.info/). Beta branches can be found in said AppID -> depots > #branches ( https://steamdb.info/app/<APPID>/depots/#branches for short ).

CS2 Dedicated server AppID = 740 - [https://steamdb.info/app/740/depots/#branches](https://steamdb.info/app/740/depots/#branches) - Available beta branches would be "1.40.2.3", "1.40.2.1", "1.40.1.4", ... , "csgo_legacy" - Avoid password protected or builds without ID / Timeupdate.

Now run PowerShell script from terminal - No need for Admin privileges. It will ask for the destination - Could be either an Existing Folder containing an App, which will prompt for to select a new location ( Will ask for a new location ), clean it ( Delete that folder and all it content and continue normaly ), update/verify it, use that location ( Will continue normaly ) or quit. If folder does not exist, it will do the same as "Delete" from before.

Then, if empty or not exitent, you will be promt to select one of the Apps in your "MyAppList.json". After that, if App has Beta defined, you will be ask if you want any.

Which ever selection you make ( except "Quit" ), will start downloading. Enjoy.

## Description
`Name` : Name of the App - Will be used for the folders name

`AppID` : AppID of the App

`Beta` : Available betas of the App. Blank = Default behaviour - Install latest stable version.
