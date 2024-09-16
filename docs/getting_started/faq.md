# FAQ

## Does Shift work only as a standalone tool?
No, Shift works also within other software like Autodesk's Maya, SideFX's Houdini and Foundry's Nuke. In time we will release more and more integrations and support for other software.

## Why are the Shift plugs outside the nodes and not inside as in other node-based tools?
When working on complex workflows, readability is very important. Having the plugs outside the nodes allows people to clearly identify and read them. With the plugs outside of the nodes we are not forced to shorten the name of plugs to fit the size of the node, which is another thing that helps readability.

## Can I see what is happening inside a Workflow Node during execution?
The progress bar in the node will indicate the percentage of the subworkflow that has been executed. Unfortunately, Shift still does not support the ability to visually expand the Workflow Node during execution. However, this is a feature that is already on our roadmap and will be delivered in a future release.

## Can I use a Shift workflow that I created using a version of Python with a Shift instance running on a different version of Python?
If you are using our in-built nodes you can trust that their behaviour will be consistent across the supported versions of Python. If your workflow uses Python Script nodes or custom nodes made by others, then the compatibility will be as good as the compatibility between those two versions of Python is.

## How do I change the name of a node?
To change the name of the node you have to select the node and then edit the name property from the properties inspector.

## I have created a Workflow Process node, but the list of available interpreters is empty. What should I do?
The Workflow Process node relies on a series of environment variables that provide the name to use for the interpreter and the path to the executable of the Python interpreter to be used. For more information, please refer to [this page](../reference/nodes/workflow#workflowprocess-node).

## Can I nest workflows using Shift?
Yes, you can use a Workflow node to point to a previously saved Shift workflow file. The node will dynamically update to show the workflow's input and output plugs. If you want to execute that nested workflow outside the main Shift process and in a different Python interpreter (e.g. mayapy) you can use the Workflow Process node instead.

## Can I use create my own catalogs of nodes for Shift?
Yes, Shift has a comprehensive API that allows you to create your own catalogs. In fact, you can even check the catalogs included in the distribution of Shift to learn more about how to define a custom catalog, or check the documentation [page here](../reference/developer_guide/developing_custom_catalogs).

## Can I define my own custom plug types?
No, unfortunately at the moment Shift does not provide an API to define custom plug types.

## Can I execute separate parts of my workflow in parallel?
No, at this moment Shift is not yet multithreaded, but we are working on an update to the execution engine that will allow that to happen.

## Can I extend the functionalities of the Shift UI?
Yes, you can create plug-ins for Shift that allow you to add custom widgets or behaviours to Shift. For more information, please refer to [this page](../reference/developer_guide/developing_custom_plugins).

## Does Shift allow me to work with USD data?
Yes, Shift has a comprehensive list of nodes designed to work with USD, allowing you to create and edit stages, prims, attributes, layers, etc. Shift even comes with a viewport to inspect the USD 3D scene and an outliner to navigate its content. To learn more about USD integration in Shift, please refer to [this page](../integration_resources/resources/USD/usd).

## Do I need to execute all the nodes from scratch every time I change something in the workflow?
No, Shift evaluates the dependency graph of your workflow in such a way that it requires executing only those nodes that were changed since the past execution.

## Does Shift have ways to troubleshoot the workflow?
Yes, Shift allows you to selectively execute parts of the workflow, or execute the nodes one step at a time. You can also set breakpoints on desired nodes in the workflow and inspect its properties at each step of the execution.

## Is Shift capable of executing parts of a workflow on a series of inputs like in a "for" loop?
Yes, shift has special [Iterator nodes](../reference/nodes/iterator) that allow you to specify the beginning and the end of the iteration block, as well as the iterable input to be used during the execution. Furthermore, Shift has a special Accumulator node that allows you to accumulate the partial results obtained during each iteration to then used them outside the iteration block.
