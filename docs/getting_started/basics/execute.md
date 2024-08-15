# Workflow Execution

This page covers all the different ways a workflow can be executed.

A node in a workflow gets executed when its been computed successfully and outputs a result. Once a node has been executed, it will be **clean** and will not be recomputed unless it gets **dirty**. A node will be dirty whenever a plug value is modified or the workflow gets saved. Shift will use dirty propagation to identify the nodes afected by the modifications done to a node and flag them to be recomputed.

## Execute All (![Execute Button](../../images/toolbar/button_execute.png){:width="25" height="25"}) 

The "Execute All" action will compute all the nodes present in the workflow. 

![Execute All](../images/execute_all.gif)

## Execute Next

The "Execute Next" action will compute the next dirty node present in the workflow. This allows to execute one node at a time and becomes useful to closely follow and inspect the processing of the workflow.

![Execute Next](../images/execute_step_by_step.gif)

## Execute Selected

The "Execute Selected" action will compute all the selected nodes in the workflow. To do so, Shift will identify the workflow sub-graph required to evaluate the desired nodes and execute it.

![Execute Selected](../images/execute_step_by_step.gif)

## Stop Execution

The "Clear Execution" action will set all the nodes in the workflow to dirty. This forces Shift to recompute all nodes the next time the workflow has to be executed. 

![Stop Execution](../images/execute_step_by_step.gif)

## Live Execution

The "Live Execution" action allows to trigger the execution of the whole workflow whenever a change to any node is done. While the "Live Execution" is turned on, the other execution buttons are disabled. To re-enable all the execution buttons, turn Live Execution off.

![Live Execution](../images/live_execution.gif)
