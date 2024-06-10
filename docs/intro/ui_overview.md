# UI Overview

This is a quick introduction to the Shift user interface.

## The Shift Window

When you open Shift you will be prompted to a window like this:

![Shift Window](../images/ui.png)

Here you have all the components that will be used to create, test and debug your workflows.  

## Toolbar

You can find the toolbar at the top-left of the window.

![Toolbar](../images/toolbar.png)

From left to right, the image contains the following buttons needed to interact with the software:

1. "*New Workflow*" - Used to start creating a new workflow from scratch
2. "*Open Workflow*" - Used to open an existing workflow file
3. "*Save*" - Used to save the current workflow file
4. "*Execute*" - Used to execute all nodes in the current workflow
5. "*Execute Selected*" - Used to execute the workflow up to the currently selected operator
6. "*Execute Next Operator*" - Used to execute the next operator in the graph
7. "*Stop Execution*" - Used to refresh the workflow execution status
8. "*Toggle Live Execution*" - Used to toggle the live execution of the workflow

## Board

Right under the toolbar you will find the Shift board. This element is what will display your workflow graph. You can interact with it to create nodes, connect them together and navigate your creation.  

**Controls**:

- "*Pan*": `Alt Key + Left-Click` or `Middle-Click`
- "*Zoom*": `Alt Key + Right-Click` or `Mouse Wheel`
- "*Focus on Selected*": `f Key`
- "*Select*": `Left-Click`
- "*Add to Selection*": `Shift Key + Left-Click`
- "*Create Node*": `Double Left-Click` or `Tab Key`
- "*Delete Selected*": `Delete Key`
- "*Recatangular Selection*": `Left-Click and Drag`

You can open as many Shift boards as you want to work on different tasks at the same time; each will be displayed as a separate tab.

## Inspector

It is used to display and modify the properties of the operators in the workflow. If we select an operator, the inspector will react displaying its properties.
The inspector is a component of the Shift window whose location and size can be customized. In our example figures it is located on the right of the main window.

![Inspector](../images/inspector.png)

Here you can customize the name of the operator and visualize or change the values of its plugs.  
The widgets in the inspector for the plug values also have a context menu accessible with `Right-Click` which will let you perform additional actions, like copying its value to the clipboard or opening a dialog showing more details.  

## Logger

Lastly in the bottom we can see the logger which will display and store all the information pertinent to your use of the software.  

![Logger](../images/logger.png)

Similarly to the inspector you can customize the location and size of this component by dragging it around.
