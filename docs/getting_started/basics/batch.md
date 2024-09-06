# Batch Execution

Shift is able to run workflows without the need of a UI interface. This is called Batch mode and can be launched via a terminal command or using the Shift Python API.

## Terminal Command

The Batch execution of a Shift workflow can be launched using the `shift_batch_lite` command located in the Shift installation root folder. Here is an example of the command syntax:

> [!NOTE = Example Command]
> === Windows
> 
> `shift_batch_lite.bat "path_to_workflow_file/workflow.sft" myInt=1 myFloat=5.6 myBool=True myList=[1, 2.5, 0.03, 'Hello World'] myString='Shift is great!'`

This command allows users to provide initialization for external inputs via a human readable format. Like it is shown in the example above, an arbitrary number of specific input plug values can be passed to the workflow by formatting the arguments of the command as `<input_plug_name>=<plug_value>`. The plug value passed by the call will then be casted to the desired Python object type depending on the type of the plug that it is being set to.

> [!WARNING]
> String type inputs must be wrapped in single quotation marks (`'`), as shown in the example above. Double quotation marks (`"`) are special characters that the OS might use to process the command syntax and can lead to unexpected behaviour.

## Shift Python API

The Shift Python API allows more flexibility when launching Batch execution of Shift workflows.

### Opening a Workflow

The following snippet of code can be used to open a Shift workflow file:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">from shift.core import files
workflow, catalog_manifest = files.openBatchWorkflow("&ltpath_to_your_workflow_file&gt")
</code></pre>


The `openBatchWorkflow `method will return the `SWorkflow` Python class containing the workflow and a Python dictionary containing the information on the Shift catalogs loaded by the workflow. Have a look at the [Shift API](../../reference/developer_guide/api.md) for more information on the method and the `SWorkflow` class.

### Executing a Workflow

Once the workflow file is opened, its execution can be triggered with the following code:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">result = workflow.execute()
</code></pre>


External inputs for the workflow can be set by providing a Python dictionary as first argument of the `workflow.execute` call. This dictionary should be formatted using the input plug names from the `Input` operator as keys and the content that should be passed as values.

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">workflow_externals = {
    "myFloatPlug1": 1.5,
    "myFloatPlug2": 9.5,
    "myBooleanPlug": True
}
result = workflow.execute(workflow_externals)
</code></pre>


The `result` variable will contain a similarly structured dictionary with the output plug names of the `Output` operator as keys and their content as values. If the workflow does not contain an Output node, the result will be `None`, for this reason it is suggested to always set up an `Input` and an `Output` operator in your workflows.

### Closing a Workflow

It is highly recommended to close the workflow after the execution is done. This process will take care of cleaning the unneeded Shift catalogs from memory. This can be performed by calling the method:

<pre><code style="white-space: pre; margin: 20px 0; padding: 10px; box-sizing: border-box;">files.closeWorkflow(workflow, catalog_manifest)
</code></pre>

