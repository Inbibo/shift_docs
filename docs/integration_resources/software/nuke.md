# Nuke

## Running Shift in Nuke

Shift provides a `nshift` utility script to properly bind the Shift UI to Nuke. In order to run and open Shift in Nuke, execute the following code block inside the Nuke *Python Script Editor*:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">import sys
sys.path.append("&ltpath_to_the_shift_installation_folder&gt")
sys.path.append("&ltpath_to_the_shift_installation_folder&gt/shift/thirdparty/python/Lib/site-packages")

from shift.tools import nshift
nshift.show()
</code></pre>


## Python Interpreter Setup
In Shift it is possible to launch the execution of a workflow via an application's Python interpreter with the [WorkflowProcess](../reference/nodes/workflow/#workflowProcess-node) node. To achieve this for Nuke, set path to its Python interpreter the following environment variables:

**SHIFT_PROCESS_NUKE** : path to Nuke’s Python interpreter (python)

## Catalogs

Shift provides some catalogs with operators specific to work within Nuke. Most of these nodes are found in the *CreativeSofware* catalog. 


<!-- ### Examples
This section is reserved to an example video of how to use Shift in Nuke.
 -->

