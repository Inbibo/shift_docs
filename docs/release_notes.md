# Release Notes

## Version 1.0.1

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
