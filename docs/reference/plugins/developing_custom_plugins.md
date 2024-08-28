# Developing Custom Plugins

Shift Plugins are developed as custom *PySide2* classes inheriting from `QtWidgets.QWidget`.

## Writing a Plugin Class

The Plugin widget class instances will always be parented to Shift's Main Window. This facilitates access to objects like the current board, the current workflow, operators, or workflow variables. To learn more about how to integrate a custom Plugin into Shift, please refer to Shift's API, especially to the application's main widget `shift.ui.widgets.main.ShiftWindow`. 

Shift's native plugins code, together with a template file can be found in the `shift/plugins` folder. These should serve as a reference for implementing your custom logic and integrating it correctly inside Shift.

Advanced users can code their own way through the Shift Python API, however it is strongly recommended to wrap all your Qt signal connections in a dedicated method (see the `MainWidget._connectBoardSignals` in the *pluginTemplate.py* example file).

```python
def _connectBoardSignals(self):
    """Standard method to connect to the current board signals."""

    # The signals to be connected from the board...e.g.
    self.parent().getActiveBoard().workflowExecuted.connect(self._updateContent)
```

This method should be run for all existing and new board tabs for the Plugin to correctly interact with Shift.

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

- the name of the top menu entry that the Plugin should be added to.
- the absolute or relative path to the Python file containing the Plugin class
- the name of the Plugin class to be imported

Shift allows users to add their custom plugins even to native menus. If a new menu name is requested, it will be added to the UI automatically.

Now that the required setups are ready, the Plugin can be sourced by appending the path to the *plugins.json* file to the `SHIFT_PLUGIN_PATH` environment variable before starting Shift. For example in *Windows*:

```cmd
set SHIFT_PLUGIN_PATH=<path_to_the_plugins_json>/plugins.json;%SHIFT_PLUGIN_PATH%
```
