# Houdini

## Running Shift in Houdini

Shift provides a `hshift` utility script to properly bind the Shift UI to Houdini. In order to run and open Shift in Houdini, execute the following code block inside the Houdini *Python Script Editor*:

```python
import sys
sys.path.append("<path_to_the_shift_installation_folder>")
sys.path.append("<path_to_the_shift_installation_folder>/shift/thirdparty/python/Lib/site-packages")

from shift.tools import hshift
hshift.show()
```

## Python Interpreter Setup
In Shift it is possible to launch the execution of a workflow via an application's Python interpreter with the [WorkflowProcess](../../reference/nodes/workflow#workflowProcess-node) node. To achieve this for Houdini, set path to its Python interpreter the following environment variable:

**SHIFT_PROCESS_HOUDINI** : path to Houdini's Python interpreter (hython)

## Catalogs

Shift provides some catalogs with operators specific to work within Houdini. Most of these nodes are found in the *CreativeSofware* catalog. 

<!-- ### Examples
This section is reserved to an example video of how to use Shift in Houdini.
 -->

