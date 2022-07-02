# tAppStore-Database
The "database" of the tizuWare App Store.

The database file may look like this (as a reference with comments):
```jsonc
{
    "LatestAppstoreVer": "1.0.0", // Newest version of the appstore
    "Apps": [
        {
            "Id": "com.yourapp", // A namespace. Has to be different from other apps
            "Name": "My App", // App display name
            "Version": "1.0.0", // App version
            "Icon": "https://...", // Link to an image that is your apps icon
            "Description": "My app is a cool app that is cool.", // Little text that tells the user what this app can do
            "RepoUrl": "https://...", // Link to your apps repo. If not provided, the button is not shown
            "BugtrackerUrl": "https://...", // Link to your apps bugtracker. If not provided, the button is not shown
            "Download": [
                {
                    "Lang": "English", // Language displayed to the user
                    "Code": "en-us", // Language code. Can be anything but has to be different from other language codes for this app
                    "Url": "https://...", // Download URL for this language or a universal installer
                },
                {
                    "Lang": "German",
                    "Code": "de-de",
                    "Url": "https://...",
                },
            ],
            "Changelog": [ // Currently unused, but provide this for being up-to-date with future versions
                {
                    "Version": "1.0.1", // Version number
                    "Text": "Bugs fixed\nSome other stuff" // List of changes
                },
                {
                    "Version": "1.0.0",
                    "Text": "Initial release"
                }
            ],
            "InstallerArgs": {
                "CommandLine": "", // Command arguments that should be passed to the installer. Can be anything
                "RequireElevation": false, // If the application should be elevated
                "DefaultPath": "", // Currently unused, but provide this for being up-to-date with future versions
                "ProvideLanguageCode": false // "{1}" will be replaced in the command arguments with the language, useful for universal installers
            },
            "InstallerMB": 0.0, // Size in MB of installer
            "ApplicationMB": 0.0, // Size in MB of application and related
            "AllowDownload": false, // If the download option should be shown, useful when server changes are planned in near future
            "Developer": "Me", // Your developer name shown to the user
            "DeveloperUrl": "https://github.com/example/" // Your developer url. If not provided, the button is not shown
        },
        {
          // Other app entry
        }
    ]
}
```
