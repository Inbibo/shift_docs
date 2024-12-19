# Release Notes

## Version 1.1.0

### Added

#### Core

- Shift workflows now run on a dedicated thread, enabling users to inspect and author other workflows and interact with the UI while there is an ongoing execution.
- An environment variable, `SHIFT_SINGLE_THREADED`, has been added to enable or disable threaded execution.
- Added a workflow execution progress bar in the Shift UI.
- Shift's board will now highlight the borders of executing boards to provide a visual cue of the execution status of a workflow.
- Added the functionality to request the interruption of an executing workflow to the "Clear Execution" button. The button will now clear the workflow only if pressed while no execution is running on the current board.
- Added a new way to rename a node by double-clicking on its name with the left mouse button.

#### Integration & Resources

- Nuke: Menu file to setup Shift tools inside Nuke.
- Nuke (Beta): "ShiftWorkflow" Nuke node to execute Shift workflow inside the Nuke node graph.

#### API

- Added `shift.utils.dcc_threading` module containing utilities to handle threaded execution in DCC context.
- Added `shift.utils.decorators` module with `mainThread` decorator for SOperator.execute methods to force execution on main thred in Maya and Nuke.
- Added `disableEditing` method to `ParameterWidget` class to enable/disable editing capabilities of the Inspector widgets.

### Improvements

#### Core

- Set Focus Execution to `False` by default. The global execution status is now tracked on the progress bar. *Shift-1218*

#### Catalogs

**Standard Catalog (Version 1.1.0)**
- Added `mainThread` boolean plug to PythonScript node to force execution on main thread in DCC context. This is needed to use DCC Python API calls for Maya or Nuke in the node's script. *Shift-1218*

**CreativeSoftware Catalog (Version 1.1.0)**
- This catalog's nodes have been made compatible with threaded execution feature in Maya. *Shift-1218*
- Added output plug to OBJImport node. *Shift-1226*

**sMayaUSD Catalog (Version 1.1.0)**
- This catalog's nodes have been made compatible with threaded execution feature in Maya. *Shift_USD-228*

### Bug Fixes

#### Core

- Fixed a bug that would break thirdparty dependencies when unloading and reloading a catalog. *Shift-1233*
- Fixed a bug that would prevent the user to run WorkflowProcess nodes with a Trial version of Shift. *Shift-1221*
- Fixed a bug that would allow users to accumulate multiple connections between the same trigger plugs. *Shift-1089*

#### Catalogs

**Workflow Catalog (Version 1.1.0)**
- Fixed a bug that would prevent the sub-workflow operators to be reset when clicking the "Clear Execution" button. *Shift-1219*

### Known Limitations

#### Integration & Resources

- Nuke: Shift interactive sessions might raise pickle errors when saving preventing the operation to be performed if the interactive instance is opened while a workflow is being run in batch mode (e.g. using the ShiftWorkflow node) in the same Python session.

---
## Version 1.0.1

### Improvements 

#### Core

- Improved compatibility of Pyarmor with third-party libraries.

### Bug Fixes

#### Core

- Fixed the logic in the Add Node operator so that it always logs any errors that may occur when creating an operator. *Shift-1173*
- Fixed the logic to set the value of an instance plug so that objects with no equivalent empty string do not fail. *Shift-1176*
- Fixed list plugs in the inspector so that their values are truncated if the plug cannot be edited. *Shift-1190*
- Fixed the creation of plugs via drag and drop so it is not possible to connect plugs with the same direction. *Shift-1189*

#### Catalogs

**Standard Catalog (Version 1.0.1)**
- Fixed the ListInsert node output plug to be initialized in the right plug direction. *Shift-1174*

**Workflow Catalog (Version 1.0.1)**
- Fixed the WorkflowProcess node so that it can be created even if no Python process environment variable is set up. *Shift-1188*

#### Integrations & Resources

- Fixed the USD Viewer Plugin to avoid the OpenGL framebuffer errors when the plugin window is detached from Shift. *Shift_USD-225*

---
## Version 1.0.0

### Added

#### Core

- Shift's workflow execution engine.
- Shift's User Interface: An interface to interact with Shift and create workflows.
- In-built catalogs:
    - Constants catalog.
    - Standard catalog.
    - FileSystem catalog.
    - Workflow catalog.
    - CreativeSoftware catalog.
- In-built plugins:
    - Nodes Outliner plugin.
    - Variables plugin.
- Workflow examples for starters.
    - float_sum.sft
    - analyse_path.sft
    - backup_files_from_dir.sft
    - get_image_sequence_frame_list.sft

#### Integrations & Resources

- Scripts to bind Shift interface to a DCC for:
    - Maya: *mshift.py*.
    - Houdini: *hshift.py*.
    - Nuke: *nshift.py*.
- USD resources:
    - In-built catalogs: sUsd, sUsdTypes, sMayaUsd.
    - In-built plugins: USD Outliner, USD Viewer.
    - Workflow examples to replicate for Pixar's USD tutorials.
