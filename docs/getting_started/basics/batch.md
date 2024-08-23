# Batch Execution

Shift is able to run workflows without the need of a UI interface. This is called Batch mode and can be used via the Shift Python API.

## Opening a Workflow

The following snippet of code can be used to open a Shift workflow file:

```python
from shift.core import files

workflow, catalog_manifest = files.openBatchWorkflow("<path_to_your_workflow_file>")
```

The `openBatchWorkflow `method will return the `SWorkflow` Python class containing the workflow and a Python dictionary containing the information on the Shift catalogs loaded by the workflow. Have a look at the [Shift API](../../reference/api.md) for more information on the method and the `SWorkflow` class.

## Executing a Workflow

Once the workflow file is opened, its execution can be triggered with the following code:

```python
result = workflow.execute()
```

External inputs for the workflow can be set by providing a Python dictionary as first argument of the `workflow.execute` call. This dictionary should be formatted using the input plug names from the `Input` operator as keys and the content that should be passed as values.

```python
workflow_externals = {
    "myFloatPlug1": 1.5,
    "myFloatPlug2": 9.5,
    "myBooleanPlug": True
}
result = workflow.execute(workflow_externals)
```

The `result` variable will contain a similarly structured dictionary with the output plug names of the `Output` operator as keys and their content as values. If the workflow does not contain an Output node, the result will be `None`, for this reason it is suggested to always set up an `Input` and an `Output` operator in your workflows.

## Closing a Workflow

It is highly recommended to close the workflow after the execution is done. This process will take care of cleaning the unneeded Shift catalogs from memory. This can be performed by calling the method:

```python
files.closeWorkflow(workflow, catalog_manifest)
```
