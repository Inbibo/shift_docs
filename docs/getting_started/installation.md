# Installation

## Portable Standalone

To install Shift on your machine simply download the .zip file build for the Python version of your liking from the [website](https://https://www.inbibo.co.uk/shift). Shift ditributions come with their own Python interpreter with all the required third-party libraries already packaged.

Once you have the folder simply unzip it in the location that you prefer and double-click on the `shift.bat` file to run it.

To run Shift using a custom Python interpreter check the [requirements](requirements.md) page.

## Maya

In order to run shift inside Maya, you need to run the following inside the Maya *Python Script Editor*:

```python
import sys
sys.path.append("<path_to_the_shift_installation_folder>")
sys.path.append("<path_to_the_shift_installation_folder>/shift/thirdparty/python/Lib/site-packages")

from shift.tools import mshift
mshift.show()
```

## Houdini

Similarly inside Houdini, you need to run the following inside the Houdini *Python Source Editor*:

```python
import sys
sys.path.append("<path_to_the_shift_installation_folder>")
sys.path.append("<path_to_the_shift_installation_folder>/shift/thirdparty/python/Lib/site-packages")

from shift.tools import hshift
hshift.show()
```

## Nuke

Inside Nuke, you need to run the following inside the Nuke *Script Editor*:

```python
import sys
sys.path.append("<path_to_the_shift_installation_folder>")
sys.path.append("<path_to_the_shift_installation_folder>/shift/thirdparty/python/Lib/site-packages")

from shift.tools import nshift
nshift.show()
```
