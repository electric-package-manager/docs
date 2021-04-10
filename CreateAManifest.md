# Creating A Package
_**❗ Important:** Creating A Manifest through the [WebUI](https://electric.sh/packages/upload/new) is easier for less advanced users!_
hpt

## Prerequisites

Electric Developer Toolkit ( `electric install --extension devtools` )

Basic Knowledge Of `JSON` (JavaScript Object Notation)

-----------------------------------------


A package manifest is a `json` file with instructions on how electric should `install` | `uninstall` | `update` a software.


We're going to be looking at how you can create a package manifest.

##  Writing Your Manifest
-----------------------------------------
Parameter : `display-name`

Type : `string`

Description : The display name of the software.

```json
{
    "display-name": "Sublime Text 3"
}
```

 _**❗ Important:**  Make sure that your display name is very similar to the Windows Registry `DisplayName` property for electric to be able to uninstall the software without any issues._

-----------------------------------------


Parameter : `package-name`

Type : `string`

Description : The package name of the software. Used with `electric install <package-name>`.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3"
}
```

_**❗ Important:** The package name cannot contain spaces because it needs to be entered from the command line._

-------------------------------
Parameter : `latest-version`

Type : `string`

Description : The latest version of the software.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211"
}
```

The latest version of a software will change when there's new releases of it.

---------------------------
Parameter : Version Specific Information

Type : `object`

Description : Defining set of information for a specific version of the software.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {}
}
```
---------------------------
Parameter : `url`

Type : `string`

Description : Link for the installer or file to be downloaded from.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {
        "url": "https://download.sublimetext.com/Sublime%20Text%20Build%203211%20x64%20Setup.exe"
    }
}
```
---------------------------
Parameter : `file-type`

Type : `string`

Description : The file type of the installer or file specified in `url`.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {
        "url": "https://download.sublimetext.com/Sublime%20Text%20Build%203211%20x64%20Setup.exe",
        "file-type": ".exe"
    }
}
```
---------------------------
Parameter : `install-switches`

Type : `list`

Description : The command line parameters passed into the installer.

Read About: [Finding Install And Uninstall Switches For Any Software](https://www.electric.sh/docs/finding-switches/)

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {
        "url": "https://download.sublimetext.com/Sublime%20Text%20Build%203211%20x64%20Setup.exe",
        "file-type": ".exe",
        "install-switches": [
            "/SP-",
            "/VERYSILENT",
            "/SUPPRESSMSGBOXES",
            "/NOCANCEL",
            "/NORESTART",
            "/FORCECLOSEAPPLICATIONS"
        ]
    }
}
```
---------------------------
Parameter : `uninstall-switches`

Type : `list`

Description : The command line parameters passed into the uninstaller.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {
        "url": "https://download.sublimetext.com/Sublime%20Text%20Build%203211%20x64%20Setup.exe",
        "file-type": ".exe",
        "install-switches": [
            "/SP-",
            "/VERYSILENT",
            "/SUPPRESSMSGBOXES",
            "/NOCANCEL",
            "/NORESTART",
            "/FORCECLOSEAPPLICATIONS"
        ],
        "uninstall-switches": [
            "/VERYSILENT", 
            "/SUPPRESSMSGBOXES", 
            "/NORESTART"
        ]
    }
}
```
---------------------------
Parameter : `custom-location`

Type : `string`

Description : The switch to be used to install the software to a custom location.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {
        "url": "https://download.sublimetext.com/Sublime%20Text%20Build%203211%20x64%20Setup.exe",
        "file-type": ".exe",
        "install-switches": [
            "/SP-",
            "/VERYSILENT",
            "/SUPPRESSMSGBOXES",
            "/NOCANCEL",
            "/NORESTART",
            "/FORCECLOSEAPPLICATIONS"
        ],
        "uninstall-switches": [
            "/VERYSILENT", 
            "/SUPPRESSMSGBOXES", 
            "/NORESTART"
        ],
        "custom-location": "/DIR="
    }
}
```
---------------------------
Parameter : `dependencies`

Type : `string`

Description : Other packages the software is dependent on.

```json
{
    "display-name": "Sublime Text 3",
    "package-name": "sublime-text-3",
    "latest-version": "3211",
    "3211": {
        "url": "https://download.sublimetext.com/Sublime%20Text%20Build%203211%20x64%20Setup.exe",
        "file-type": ".exe",
        "install-switches": [
            "/SP-",
            "/VERYSILENT",
            "/SUPPRESSMSGBOXES",
            "/NOCANCEL",
            "/NORESTART",
            "/FORCECLOSEAPPLICATIONS"
        ],
        "uninstall-switches": [
            "/VERYSILENT", 
            "/SUPPRESSMSGBOXES", 
            "/NORESTART"
        ],
        "custom-location": "/DIR=",
        "dependencies": []
    }
}
```
---------------------------

That's it! Now all you've got to do is submit the package for moderation!
