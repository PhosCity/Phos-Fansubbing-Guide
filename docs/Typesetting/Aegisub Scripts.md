# Aegisub Scripts

Aegisub scripts are Lua or Moonscript files that can be used to automate tedious,
repetitive, or complex tasks. These scripts are absolutely mandatory for typesetting because using them will increase your efficiency.

There are two methods of installing Aegisub scripts:
Automatic and Manual.

## Folder where Aegisub scripts are stored

All scripts must be located in the automation folder of Aegisub. For different
operating systems, this folder is located in different directories.

| Operating System | Automation Directory |
| -------------- | --------------- |
|Windows |`%appdata%\Aegisub\` |
|Linux |`$HOME/.aegisub/`|
|MacOS |`$HOME/Library/Application Support/Aegisub/`|

For Windows users to go to this directory, press ++win+"r"++ in your keyboard
and type `%appdata%\Aegisub` in the textbox and hit ++enter++. For MacOS users,
press ++cmd+shift+"g"++, type `~/Library/Application Support/Aegisub` to do the same.

Inside this folder, there must be a folder called __automation__. Inside
__automation__ folder, there must be two folders: __autoload__ and __include__.
If you are manually installing scripts, and any of these folders are missing,
create those folders yourself. The folder __autoload__ consists of all the
scripts that you want Aegisub to load while the folder __include__ consists of
all the modules that the scripts depend on.

If you have a portable installation of Aegisub, the __automation__ folder is
located in the same directory as the Aegisub installation.

## Automatic Method

This is the recommended method of installing Aegisub scripts as it allows you to
install, uninstall and update scripts without ever leaving Aegisub. The tool that
achieves this is called [Dependency Control](https://github.com/TypesettingTools/DependencyControl).
On Windows, newer versions of Aegisub are shipped with Dependency Control already
included. If your installation of Aegisub does not contain Dependency Control, you
can follow the steps below to install it.

### Installation of Dependency Control

1. Windows and Mac users can download the latest Dependency Control files from the
   latest release from it’s [repo](https://github.com/TypesettingTools/DependencyControl/releases).
   In this page, click on __Assets__ and click on the file for your respective
   operating system. Linux users must compile Dependency Control on their own.
   (Arch Linux users may use
   [AUR package](https://aur.archlinux.org/packages/aegisub-dependency-control )
   instead)
1. Extract the Dependency Control files in the Aegisub’s automation directory.
1. Restart Aegisub.

### Using Dependency Control to install scripts

1. In Aegisub, go to `Automation -> DependencyControl -> Install Script`.
1. In the first drop-down menu called __Automation Scripts__, select the script you
   want to download and click __OK__.

Let's install a script called `Edit Tags` from Dependency Control.

<video width="2546" height="1546" controls>
  <source src="../assets/Aegisub Script/install_edit_tags.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

In the video above, I install the script from Dependency Control and then rescan
the autoload directory. After the rescan, `Edit Tags` can be seen in `Automation -> Edit Tags`.

## Manual Method

Not all Aegisub scripts have been added to Dependency Control. In order to
install those scripts, you will have to manually download the script and move it
to the required folders.

1. Download the script to your computer. If your script depends on some modules,
   download them as well.
1. Copy the script to the __autoload__ directory. Copy the modules to __include__
   directory.
1. Restart Aegisub

## Global and local scripts

Global scripts are the scripts that are available in the automation folder. When
Aegisub opens, these scripts are automatically loaded.

Local scripts are the scripts that are manually added by the user. These scripts
can be located in any directory and are linked to the subtitle file that is open
when the script was added. When you open a subtitle file that is linked with a
local script, that script will be loaded. Similarly, when you close that subtitle
file, all the local scripts linked to it will be unloaded.

## Automation Manager

The automation manager is a window that can be used to manage all the scripts you
have installed. To open the Automation Manager in Aegisub, go to `Automation -> Automation...`

<!-- [[File:Automation Manager.png|center]] -->

The scripts that have __G__ in the leftmost column are global scripts. The scripts
that have __L__ are the local scripts.

Local scripts can be added to the currently opened subtitle file using the
__Add__ button, and they can be removed using the __Remove__ button. Any script
that is already loaded into Aegisub can be reloaded individually using __Reload__
button. Finally, __Rescan Autoload Directory__ will scan the autoload folder
and load all the global scripts again.

## Reloading Aegisub scripts

Aegisub loads all the scripts it finds in its autoload directory during startup.
If you installed a script while Aegisub is open, Aegisub is not going to load it
automatically. There are two ways to reload the scripts. One is to simply closing
and reopening Aegisub. If you want to load the script without closing Aegisub,
go to __Automation Manager__ and click on __Rescan Autoload Directory__ button

Alternatively, you can also add a hotkey to reload. Adding a hotkey to command
`am/reload` will rescan autoload folder and reload both global and local scripts.
Adding a hotkey to command `am/reload/autoload` will only rescan autoload folder.

## Errors during installing scripts

After installing a script, the first time they are loaded in Aegisub, you might
come across an error message for all the scripts that failed to load. The errors
might occur due to following reasons:

1. Errors in the script itself.
1. The script depends on some external modules, but it cannot find them in the
   proper location.

Clicking __Details__ will always give you more information. It tells you what the
error is which will give you a hint on how to fix it. If the error is about missing
files, it can always be fixed by moving required files in required directory.
Other errors will need to be dealt on case by case basis.

## Binding Aegisub Script to Hotkey

Every time you run a script, you don't want to go to `Automation` and click on
the script name. This is why we bind a script to a hotkey so that all you need
to do to run a script is press a key. Using hotkeys is a must so learn here how
you bind a script to hotkey. I'll not be explaining it for each script.

1. In Aegisub, go to `View -> Options -> Interface -> Hotkeys`.
1. Click on `Subtitle Grid`
1. Click on the button `New`
1. Then, in the `Hotkey` column i.e. the left column, click the key in the keyboard
   that you want to bind the script to. For example, I want to run the script
   `Edit Tags` whenever I press `E` in `Subtitle Grid`. So I'll press E in the
   left column.
1. Then I'll type `automation/lua` in the middle column. A dropdown will appear
   where you can select Edit Tags. You can type more to refine the selection.
1. Click `OK` key.
1. Now whenever you press the key in left column, the command in middle column
   will be  executed.

<video width="2546" height="1546" controls>
  <source src="../assets/Aegisub Script/hotkey_edit_tags.mp4" type="video/mp4">
Your browser does not support the video tag.
</video>

!!! note

    What key you bind to what script is your choice. I personally tend to bind
    the first key of the script's name to that key. `E` for Edit Tags. It is easier
    to remember.

