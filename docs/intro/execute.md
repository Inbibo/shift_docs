# Executing Your Workflow

You can execute your workflow in different ways:

Click the “Execute” button (![Execute Button](../images/toolbar/button_execute.png){:width="25" height="25"}). You should see the nodes progress bars lighting up.

![Execute All](../images/execute_all.gif)

Shift uses dirty propagation to determine which nodes need to be recomputed. Whenever a plug value on a node is modified, that node is set to be recomputed in the next execution. You can force Shift to recompute all nodes by pressing the “Stop Execution” button (![Stop Execution](../images/toolbar/button_executeStop.png){:width="30" height="30"}).

It is also possible to execute a workflow step-by-step. Simply press the “Execute Next Operator” button (![Execute Next Button](../images/toolbar/button_executeNext.png){:width="30" height="30"}) to see the workflow being executed one node at a time.

![Execute Step by Step](../images/execute_step_by_step.gif)

The execution can also be forced on selected nodes. By selecting the desired nodes and pressing the “Execute Selected” button (![Execute Selected Button](../images/toolbar/button_executeSelected.png){:width="30" height="30"}), Shift will identify the workflow sub-graph required to evaluate the desired nodes and execute it.

Finally, it is also possible to trigger the execution of a workflow whenever a change to any node is done by using the live execution option. Press the “Toggle Live Execution” button (![Live Execute](../images/toolbar/button_executeLiveOff.png){:width="30" height="30"}) and Shift will execute the workflow automatically every time a change is being made.

![Live Execution](../images/live_execution.gif)

While the Live Execution is turned on, the other execution buttons are disabled. To re-enable all the execution buttons, turn Live Execution off.
