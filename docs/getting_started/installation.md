# Installation

To install Shift, download the *.zip* file corresponding to the preferred Python version from the [website](https://https://www.inbibo.co.uk/shift). Shift distributions packages come with a built-in Python interpreter, along with all necessary third-party libraries to use Shift and its native catalogs.

After downloading the package, unzip the folder to the desired location and double-click the `shift.bat` file to launch the application.

> [!NOTE]
>  It is recommended to add the following environment when installing Shift. Not adding this will not prevent the basic features of Shift from working, but is needed for Shift's special node [WorkflowProcess](../reference/nodes/workflow#workflowproces-node).
> - **SHIFT_PROCESS_PYTHON**: Used by the WorkflowProcess node to retrieve the path to a Python interpreter. The value of this environment variable should be the path to a Python interpreter.

For running Shift with a custom Python interpreter, refer to the [requirements](requirements.md) page.

<!-- TODO #44 -->
