# Davinci Resolve

## Running Shift in Davinci Resolve

Shift can be integrated in Davinci Resolve and used to automatize editorial process using all the catalog provided with Shift, but specially the Shift_Resolve catalog.

<figure>
      <img src="images/resolve_shift_ui.png" alt="Resolve Shift UI">
      <figcaption><b>Figure 1</b>: Shift UI in Davinci Resolve.</figcaption>
</figure>

To run Shift inside Davinci Resolve is required to set up the configuration required by Blackmagic to have the ability of execution python code inside Resolve. 

## Python Interpreter Setup

Blackmagic usually provides a `Readme.txt` file where these requirements are detailed for the version in use in the installation folder `C:\ProgramData\Blackmagic Design\DaVinci Resolve\Support\Developer\Scripting\Readme.txt`

Apart from the official requirements, the `PYTHONHOME` environment is required to be set. It must point to the python interpreter to be used in Resolve.

To use the Python interpreter provided with Shift, set up the variable in this way:

**SHIFT_PROCESS_NUKE** : <path_to_your_shift_folder>/shift/thirdparty/python

## Shift Menu

The Resolve Script menus for python files are limited to add entries to the section of `Workspace>Scripts` and split by workspaces layouts inside.

To add a new entry and have a Shift menu in Resolve, is required to add a python script to the Resolve Scripts folder. This folder can be different for each Resolve version, and it's recommended to check the right directory for the version that is being used. However, typically the folder is located in this locations:

Mac OS X:
  - All users: /Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Scripts
  - Specific user:  /Users/<UserName>/Library/Application Support/Blackmagic Design/DaVinci Resolve/Fusion/Scripts
Windows:
  - All users: %PROGRAMDATA%\Blackmagic Design\DaVinci Resolve\Fusion\Scripts
  - Specific user: %APPDATA%\Blackmagic Design\DaVinci Resolve\Support\Fusion\Scripts
Linux:
  - All users: /opt/resolve/Fusion/Scripts  (or /home/resolve/Fusion/Scripts/ depending on installation)
  - Specific user: $HOME/.local/share/DaVinciResolve/Fusion/Scripts

To add Shift, is required to create a Python Script inside one workspace folder, `Edit` for example. The Python file name will be used like menu name too, soo name the file `Shift`.

For a windows local user, the result path for the file will be this one:
`%APPDATA%\Blackmagic Design\DaVinci Resolve\Support\Fusion\Scripts\Edit\Shift.py`

Inside the file, add the following code:

```python
from shift.tools import shiftui
shiftui.show()
```

With this file saved, Resolve will show a Shift menu that can be executed to open the Shift UI inside Davinci Resolve.

<figure>
      <img src="images/resolve_shift_menu.png" alt="Shift Menu">
      <figcaption><b>Figure 2</b>: Shift Menu on Davinci Resolve's top menu bar.</figcaption>
</figure>

## Catalogs

Shift provides a catalog with operators specific to work within Davinci Resolve. This catalog is not zipped with the main instalation of Shift, but it can be access and downloaded from [Shift_Resolve](https://github.com/Inbibo/Shift_Resolve).
