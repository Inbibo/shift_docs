# Workflow Execution

The execution of a node in a Shift workflow consist in the evaluation of its internal logic given the node's input data. If the execution completes successfully, the output plugs will be updated with the result and the node will be flagged as **clean**. All clean nodes will be displayed with a full blue progress bar and will not be recomputed unless they become **dirty**. The dirty status is set whenever a plug value is modified or the workflow gets saved or manually reset via the Shift UI. Shift will use dirty propagation to identify the nodes affected by the modifications done to a node and flag them to be recomputed.

There are different ways a workflow can be executed, which depend on which nodes will get computed. 

## ![Execute All Button](images/toolbar/execute_all_default.svg){:width="25" height="25"} Execute All

The "Execute All" action will compute all the dirty nodes present in the workflow. 

<figure>
      <img src="images/execute_all.gif" alt="Execute All">
      <figcaption><b>Figure 1</b>: Executing all the workflow.</figcaption>
</figure>


## ![Execute Selected Button](images/toolbar/execute_selected_default.svg){:width="25" height="25"} Execute Selected

The "Execute Selected" action will compute all the selected nodes in the workflow. To do so, Shift will identify the workflow sub-graph required to evaluate the desired nodes and execute it.

<figure>
      <img src="images/execute_selected.gif" alt="Execute Selected">
      <figcaption><b>Figure 2</b>: Executing the workflow up to the selected node.</figcaption>
</figure>


## ![Execute Next Button](images/toolbar/execute_next_default.svg){:width="25" height="25"} Execute Next

The "Execute Next" action will compute the next dirty node present in the workflow. This allows to execute one node at a time and becomes useful to closely follow and inspect the processing of the workflow.

<figure>
      <img src="images/execute_step_by_step.gif" alt="Execute next">
      <figcaption><b>Figure 3</b>: Executing the workflow one step at a time.</figcaption>
</figure>


## ![Clear Execution Button](images/toolbar/clear_all_default.svg){:width="25" height="25"} Clear Execution

The "Clear Execution" action will set all the nodes in the workflow to dirty. All **connected** inputs and output values will be cleared to their default values. This forces Shift to recompute all nodes the next time the workflow has to be executed. 

<figure>
      <img src="images/clear_execution.gif" alt="Clear execution">
      <figcaption><b>Figure 4</b>: Clear the executed status from all nodes.</figcaption>
</figure>


## ![Live Execution Button](images/toolbar/execute_live_default.svg){:width="25" height="25"} Live Execution

The "Live Execution" action allows to trigger the execution of the whole workflow whenever a change to any node is done. While the "Live Execution" is turned on, the other execution buttons are disabled. To re-enable all the execution buttons, turn Live Execution off.

<figure>
      <img src="images/live_execution.gif" alt="Live Execution">
      <figcaption><b>Figure 5</b>: Executing workflow in live execution mode.</figcaption>
</figure>

