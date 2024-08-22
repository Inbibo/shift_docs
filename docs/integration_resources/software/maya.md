# Maya

## Running Shift in Maya

Shift provides a `mshift` utility script to properly bind the Shift UI to Maya. In order to run and open Shift in Maya, execute the following code block inside the Maya *Python Script Editor*:

```python
import sys
sys.path.append("<path_to_your_shift_folder>")
sys.path.append("<path_to_your_shift_folder>/thirdparty/python/Lib/site-packages")

from shift.tools import mshift
mshift.show()
```

## Python Interpreter Setup
In Shift it is possible to launch the execution of a workflow via an application's Python interpreter with the [WorkflowProcess](../reference/nodes/workflow/#workflowProcess-node) node . To achieve this for Maya, set the path to its python interpreter in your environment variables:

`SHIFT_PROCESS_MAYA : path to Maya’s Python interpreter (mayapy)`

## Catalogs

Shift provides some catalogs with operators specific to work within Maya. Most of these nodes are found in the *CreativeSofware* catalog. Additionally, the following Shift catalogs also provide support specific nodes for Maya:

* [Shift_3D](https://github.com/Inbibo/Shift_3D)

<!-- ### Examples
This section is reserved to an example video of how to use the Python Script node.
 -->

