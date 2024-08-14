# Your Shift Development

## Creating a Catalog

With shift you can create your own customized catalog with nodes tailored for your specific usecase and softwares.

A custom catalog can be written in Python and it must contain a global variable called `catalog` which is a Python dictionary containing the information on the catalog which will be displaied by Shift and a list with the index with the operator classes inside the file.
Here is an example from the Shift's *Constants* catalog:

```python
catalog = {"Description": "This catalog includes fundamental Python type operators.",
           "Version": "1.0.0",
           "Author": "Shift's development team", 
           "Operators":[[String,  []],
                        [Integer, []],
                        [Float,   []],
                        [Bool,    []]]}
```

A catalog must be then sourced in Shift either by using the *Catalog Manager* from the Shift UI or by adding the path to the folder containing the catalog file to the `SHIFT_CATALOG_PATH` environment variable.

## Operator Syntax

Inside the catalog file you can create your custom operators as Python classes. Here is an example of its syntax:

```python
from shift.core.workflow import SOperator
from shift.core.workflow import SPlug
from shift.core.constants import SType
from shift.core.constants import SDirection

class MyOperator(SOperator):

    def __init__(self, code, parent=None):

        super(self.__class__, self).__init__(code, parent)

        inPlug1 = SPlug(code="input1",
                       value=0,
                       type=SType.kInt,
                       direction=SDirection.kIn,
                       parent=self)

        inPlug2 = SPlug(code="input2",
                       value=0,
                       type=SType.kInt,
                       direction=SDirection.kIn,
                       parent=self)

        outPlug = SPlug(code="output",
                       value=0,
                       type=SType.kInt,
                       direction=SDirection.kOut,
                       parent=self)

        self.addPlug(inPlug1)
        self.addPlug(inPlug2)
        self.addPlug(outPlug)

    def execute(self, force=False):

        input1 = self.getPlug("input1", SDirection.kIn).value()
        input2 = self.getPlug("input2", SDirection.kOut).value()

        output = input1 * input2

        self.getPlug("output").setValue(output)
        super(self.__class__, self).execute(force)
```

The example operator's constructor method takes care of initalizing the plug objects and adding them to the operator. Each plug must be initialized specifying its type (which in this case is `SType.kInt`) and a direction which can be either `SDirection.kIn` or `SDirection.kOut`.

The **execute** method takes care of defining the list of steps to be performed when the execution of the operator is issued inside Shift. In the example the execute method picks up the values of the two input plugs and mutliplies them together. Finally it stores the result in the output plug.

Please refer to the Shift API documentation to know more about which plug types are present in Shift, and which additional methods the `SPlug` and `SOperator` classes offer.

## Creating a Plugin

Finally Shift allows you to create your own Qt-based custom tools that can be integrated in the Shift interface, to allow visual feedback or interaction for your workflows. An example of this could be the *Usd Outliner* from *Shift_USD* which allows the user to traverse the Usd Stages loaded by the catalog Operators and visualize the Prim hierachy.

Similarly to the custom catalog you can create your custom Plugin for Shift in a Python file. The Plugin must follow the syntax in the example in order for it to correctly communicate with the Shift operators and interface:

```python
from PySide2 import QtWidgets

class MyPlugin(QtWidgets.QDialog):

    def __init__(self, parent=None):
        super(MyPlugin, self).__init__(parent)

        <your_qt_logic>

        # Connect the Qt Signals from Shift
        self.getShiftBoard().currentChanged.connect(self.myUpdateUIMethod)
        self.getMainWindow().newBoardCreated.connect(self.connectBoardSignals)

    def getMainWindow(self):
        return self._mainWindow

    def getShiftBoard(self):
        return self._mainWindow._boardTabsWidget

    def connectBoardSignals(self):
        """Method to connect Qt signals when a new board is created."""
        self.getShiftBoard().currentWidget().workflowExecuted.connect(self.myUpdateUIMethod)
        self.getShiftBoard().currentWidget().nodeSelected.connect(self.myUpdateUIMethod)
        self.getShiftBoard().currentWidget().nodeRenamed.connect(self.myUpdateUIMethod)
        self.myUpdateUIMethod()

    def myUpdateUIMethod(self):

        <your_qt_update_logic>
```

This is a basic implementation example to show how the interaction with the Shift UI with Qt signals should be initialized. The `MyPlugin` class is parented to the Shift Main Window which gives us access to certain signals for the global interaction with the Shift UI (like `newBoardCreated`). Then the workflow specific actions like node selection, node removal or workflow execution are controlled by the specific Shift board which contains the operators we are working with. As each board in Shift is a separate Python instance, we must connect its signals every time a new board is created. We suggest to organize this logic in the `connectBoardSignals` method like in the example code. An API `SPlugin` class will come in the future to take care of simplifying the implementation of this logic.

Plugins need an additional file to setup the information needed by Shift to integrate the Plugin in the UI.
Such file is a *json* and should be called `plugins.json`. Here is an example of its content:

```json
"My Plugin": {
        "menu": "My Menu",
        "path": "<path_to_the_plugin_file>/myPlugin.py",
        "class": "myPlugin",
    },
"My Other Plugin": {
        "menu": "My Menu",
        "path": "<path_to_the_plugin_file>/myOtherPlugin.py",
        "class": "myOtherPlugin"
    }
```

As we can see from the example in this file we can list several plugins to be initialized and specify the path to the python file containing the specific Plugin class and the top menu to add the new entry to. If the mentioned menu is not present already, Shift will take care of creating it for you.

Here is an example of how the plugin menu entry will look like:

![Plugin Menu UI Example](../../images/dev_help/plugin_menu_ui_example.png)
