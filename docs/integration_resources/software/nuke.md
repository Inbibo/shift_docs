# Nuke

## Running Shift in Nuke

Shift provides a `nshift` utility script to properly bind the Shift UI to Nuke. In order to run and open Shift in Nuke, execute the following code block inside the Nuke *Python Script Editor*:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">import sys
sys.path.append("&ltpath_to_the_shift_installation_folder&gt")
sys.path.append("&ltpath_to_the_shift_installation_folder&gt/shift/thirdparty/python/Lib/site-packages")

from shift.tools import nshift
nshift.show()
</code></pre>

## Shift installation in Nuke

To install Shift and open it through a menu entry within Nuke, it is required to set up Shift in the environment or in the user *init.py* Python files from Nuke. Shift can be added to the user *init.py* file from Nuke's preference folder (*<home directory>/.nuke*) or to a custom *init.py* file inside a custom folder structure. If the directory where these files are stored is a path sourced by Nuke, they will be automatically executed on startup.

### Init File/Environment requirements

You can add these requirements to your environment before opening Nuke:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">
PATH=&#37PATH&#37;"&ltpath_to_the_shift_installation_folder&gt"
PATH=&#37PATH&#37;"&ltpath_to_the_shift_installation_folder&gt/shift/thirdparty/python/Lib/site-packages"
NUKE_PATH="&ltpath_to_the_shift_installation_folder&gt/shift/plugins/nuke/startup";&#37NUKE_PATH&#37

</code></pre>

Or you can add them to the *init.py* file to make Shift to work in Nuke batch and interactive modes. To achieve this, it is only required to add the Shift installation path to the **PATH** environment variable.

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">
import nuke

try:
    import shift
except:
    import sys
    sys.path.append("&ltpath_to_the_shift_installation_folder&gt")
    sys.path.append("&ltpath_to_the_shift_installation_folder&gt/shift/thirdparty/python/Lib/site-packages")

nuke.pluginAddPath("&ltpath_to_the_shift_installation_folder&gt/shift/plugins/nuke/startup")
</code></pre>

>[!NOTE]
> If the paths are added at the system level or before opening Nuke, then this configuration step will not be required.

## Shift in Nuke

When the requirements are added you will Shift a Shift menu entry in the toolbar and top menu inside Nuke.

This entry will contain the access to open the Shift UI and to create a ShiftWorkflow Node.

<figure>
      <img src="images/nuke_shift_toolbar.png" alt="Shift Toolbar">
      <figcaption><b>Figure 1</b>: Shift *menu.py* entry in the Nuke Nodes Toolbar.</figcaption>
</figure>

<figure>
      <img src="images/nuke_shift_menu.png" alt="Shift *menu.py*">
      <figcaption><b>Figure 2</b>: Shift *menu.py* on Nuke's top *menu.py* bar.</figcaption>
</figure>

## Python Interpreter Setup
In Shift it is possible to launch the execution of a workflow via an application's Python interpreter with the [WorkflowProcess](../../reference/nodes/workflow#workflowProcess-node) node. To achieve this for Nuke, set the path to its Python interpreter the following environment variables:

**SHIFT_PROCESS_NUKE** : path to Nuke's Python interpreter (*python*).

The variable can be set in any environment to be able to execute Shift Workflows in Nuke from standalone or other DCC instances.


## Catalogs

Shift provides some catalogs with operators specific to work within Nuke. Most of these nodes are found in the [CreativeSoftware](../../reference/catalogs/shift_catalogs/creativesoftware) catalog. 


<!-- ### Examples
This section is reserved to an example video of how to use Shift in Nuke.
 -->

