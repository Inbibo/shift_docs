# Nuke

## Running Shift in Nuke

Shift provides a `nshift` utility script to properly bind the Shift UI to Nuke. In order to run and open Shift in Nuke, execute the following code block inside the Nuke *Python Script Editor*:

```python
import sys
sys.path.append("<path_to_the_shift_installation_folder>")
sys.path.append("<path_to_the_shift_installation_folder>/shift/thirdparty/python/Lib/site-packages")

from shift.tools import nshift
nshift.show()
```

## Python Interpreter Setup
In Shift it is possible to launch the execution of a workflow via an application's Python interpreter with the [WorkflowProcess](../reference/nodes/workflow/#workflowProcess-node) node. To achieve this for Nuke, set path to its Python interpreter the following environment variables:

**SHIFT_PROCESS_NUKE** : path to Nuke’s Python interpreter (python)

## Catalogs

Shift provides some catalogs with operators specific to work within Nuke. Most of these nodes are found in the *CreativeSofware* catalog. 


<!-- ### Examples
This section is reserved to an example video of how to use Shift in Nuke.
 -->

