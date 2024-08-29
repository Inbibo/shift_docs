# Developing Custom Plugins

Shift Plugins are developed as custom *PySide2* classes inheriting from `QtWidgets.QWidget`.

## Writing a Plugin Class

The Plugin widget class instances will always be parented to Shift's Main Window. This facilitates access to objects like the current board, the current workflow, operators, or workflow variables. To learn more about how to integrate a custom Plugin into Shift, please refer to Shift's API, especially to the application's main widget `shift.ui.widgets.main.ShiftWindow`.

Shift's native plugins code, together with a template file can be found in the `shift/plugins` folder. These should serve as a reference for implementing your custom logic and integrating it correctly inside Shift.

Advanced users can code their own way through the Shift Python API, however it is strongly recommended to follow these design principles:

- Store the widget parent in a class property. After the initialization of the widget class, Shift will change the parenting hierarchy. For this reason it is strongly suggested to store the parent object in the Plugin class constructor. At initialization time, the parent will correspond to the *ShiftWindow* object.

```python
  class MainWidget(QtWidgets.QWidget):
      """Main plugin widget.

      @param parent shift.ui.widgets.main.ShiftWindow: The Shift main window.

      """
      def __init__(self, parent=None):
          super(MainWidget, self).__init__(parent)

          #Store the ShiftWindow inside a class property
          self.mainWindow = parent
```

- Wrap all the Qt signal connection calls to the board in a dedicated method (see the `MainWidget._connectBoardSignals` in the *pluginTemplate.py* example file). As each workflow board propagates its own Qt signals, connections must be performed for all existing boards and new ones.

```python
  def _connectBoardSignals(self):
      """Standard method to connect to the current board signals."""

      # The signals to be connected from the board...e.g.
      self.mainWindow.getActiveBoard().workflowExecuted.connect(self._updateContent)
```

This method should be executed for all existing and new board tabs for the Plugin to correctly interact with Shift. The ideal way to do that is to use this method as a Qt slot and connect it to the following signals at the end of the Plugin class constructor logic:

```python
  def __init__(self, parent=None):

      [...]

      self.mainWindow.getBoardTabsWidget().currentChanged.connect(self._connectBoardSignals)
      self.mainWindow.newBoardCreated.connect(self._connectBoardSignals)
      self._connectBoardSignals()
```

This will automatically connect the board signals to the currently active one and brand new ones.

## Adding the Plugin to Shift

The first step to add the Plugin to the Shift UI is to create a *json* file containing the information needed by Shift to source all of the custom Plugin classes. This file should be formatted in the following way:

```json
{
  "Operators List": {
    "menu": "Tools",
    "path": "./operatorsList.py",
    "class": "OperatorsList"
  },
  "Variables Browser": {
    "menu": "Tools",
    "path": "./variablesBrowser.py",
    "class": "VariablesBrowser"
  }
}
```

Each Plugin main entry name will define the name displayed by the Plugin menu entry in the top bar menu. Then for each Plugin entry will need:

- The name of the top menu entry that the Plugin should be added to.
- The absolute or relative path to the Python file containing the Plugin class.
- The name of the Plugin class to be imported.

Shift allows users to add their custom plugins even to native menus. If a new menu name is requested, it will be added to the UI automatically.

Once the *json* file is created and populated, the Plugin can be sourced by appending the path to the *plugins.json* file to the `SHIFT_PLUGIN_PATH` environment variable before starting Shift:

**SHIFT_PLUGIN_PATH** : "<path_to_the_plugins_json>/plugins.json"
