# Houdini

## Running Shift in Houdini

Shift provides a `hshift` utility script to properly bind the Shift UI to Houdini. In order to run and open Shift in Houdini, execute the following code block inside the Houdini *Python Script Editor*:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">try:
    import shift
exception:
    import sys
    sys.path.append("&ltpath_to_the_shift_installation_folder&gt")
    sys.path.append("&ltpath_to_the_shift_installation_folder&gt/shift/thirdparty/python/Lib/site-packages")

from shift.tools import hshift
hshift.show()
</code></pre>


## Python Interpreter Setup
In Shift it is possible to launch the execution of a workflow via an application's Python interpreter with the [WorkflowProcess](../../reference/nodes/workflow#workflowProcess-node) node. To achieve this for Houdini, set the path to its Python interpreter the following environment variable:

**SHIFT_PROCESS_HOUDINI** : path to Houdini's Python interpreter (hython)

## Catalogs

Shift provides some catalogs with operators specific to work within Houdini. Most of these nodes are found in the [CreativeSoftware](../../reference/catalogs/shift_catalogs/creativesoftware) catalog. 

<!-- ### Examples
This section is reserved to an example video of how to use Shift in Houdini.
 -->

