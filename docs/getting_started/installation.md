# Installation

## Windows

To install Shift in Windows, download the *.zip* distribution file for Windows from the [website](https://www.inbibo.co.uk/shift). Shift distribution packages come with a built-in Python interpreter, along with all necessary third-party libraries to use Shift and its native catalogs.

After downloading the package:

    1. Uncompress the folder to the desired location
    2. Open the "shift" folder
    3. Double-click the `shift.bat` file to launch the application

## Linux

To install Shift in Linux, download the *.tar.gz* distribution file for linux from the [website](https://www.inbibo.co.uk/shift). Shift distribution packages come with a built-in Python interpreter, along with all necessary third-party libraries to use Shift and its native catalogs.

After downloading the package:

    1. Uncompress the folder to the desired location
    2. Open a terminal window and `cd` inside the "shift" folder
    3. Execute `./shift.sh`

> [!NOTE]
>  It is recommended to add the following environment when installing Shift. Not adding this will not prevent the basic features of Shift from working, but it is needed for Shift's special [WorkflowProcess](../reference/nodes/workflow#workflowproces-node) node.
> - **SHIFT_PROCESS_PYTHON**: Used by the WorkflowProcess node to retrieve the path to a Python interpreter. The value of this environment variable should be the path to a Python interpreter.

For running Shift with a custom Python interpreter, refer to the [requirements](requirements) page.
